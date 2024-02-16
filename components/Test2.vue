<template>
    <div>
        <h1>Test</h1>
        <NuxtIcon name="account" />
        <div ref="animationContainer" class="lottie-animation-container" />
        <button>jo</button>
    </div>
</template>

<script setup lang="ts">
import Lottie from "lottie-web";
import { isCollecting } from 'histoire/client'

const animationContainer = ref<HTMLElement>();
onMounted(() => {
    if (!isCollecting() && animationContainer.value) {
        Lottie.loadAnimation({
            container: animationContainer.value,
            renderer: "svg",
            loop: true,
            autoplay: true,
            path: "<path d='M150 0 L75 200 L225 200 Z' style='fill:none;stroke:green;stroke-width:3' />",
        });
    }
});
</script>
<style lang="scss"></style>
