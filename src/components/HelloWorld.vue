<template>
    <div class="hello">
        <h2>{{ state.messageOne }}</h2>
        <h2>{{ messageTwo }}</h2>
    </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";

export default defineComponent({
    name: "HelloWorld",
    setup() {
        // reactiveとrefの使用方法
        // 既存のものだとdataにあたるもの
        const state = reactive<{ messageOne: string }>({
            messageOne: "Hello",
        });

        const messageTwo = ref<string>("こんにちは");

        return {
            state,
            messageTwo,
        };
    },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
