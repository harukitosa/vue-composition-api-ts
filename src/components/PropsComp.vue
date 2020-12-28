<template>
    <div class="hello">
        <button @click="upperCaseMessage">To upperCase</button>
    </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, SetupContext } from "vue";

type Props = {
    message: string;
};
export default defineComponent({
    props: {
        message: {
            type: String,
            default: "default value",
        },
    },
    setup(props: Props, context: SetupContext) {
        const upperCaseMessage = () => {
            context.emit("change-message", props.message.toUpperCase());
        };

        return {
            upperCaseMessage,
        };
    },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
