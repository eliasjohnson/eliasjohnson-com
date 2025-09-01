<svelte:head>
    <script type="module" src="https://unpkg.com/@splinetool/viewer@1.9.50/build/spline-viewer.js"></script>
</svelte:head>

<script lang="ts">
    export let sceneId: string;
    export let className: string = '';
</script>

<spline-viewer 
    url="https://prod.spline.design/{sceneId}/scene.splinecode"
    events-target="global"
    class={className}>
</spline-viewer>

<style>
    spline-viewer {
        width: 100%;
        height: 100%;
        display: block;
    }
</style>