<template>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld />
    <h1>{{ state.message }}</h1>
    <PropsComp :message="state.message" @change-message="changeMessage" />
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import PropsComp from "./components/PropsComp.vue";

export default defineComponent({
    name: "App",
    components: {
        HelloWorld,
        PropsComp,
    },
    setup() {
        const state = reactive({
            message: "Hello",
        });

        const changeMessage = (message: string) => {
            state.message = message;
        };

        return {
            state,
            changeMessage,
        };
    },
});
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
