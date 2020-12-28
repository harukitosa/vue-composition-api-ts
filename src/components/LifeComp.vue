<template>
    <div class="hello"></div>
</template>

<script lang="ts">
import { defineComponent, onMounted, onUnmounted, onUpdated } from "vue";

export default defineComponent({
    setup() {
        onMounted(() => {
            console.log("mounted");
        });

        onUpdated(() => {
            console.log("updated");
        });

        onUnmounted(() => {
            console.log("unmounted");
        });
    },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
