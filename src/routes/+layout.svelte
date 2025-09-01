<script lang="ts">
    import { page } from '$app/stores';
    import { onMount } from 'svelte';
    
    // Global Spline background
    const splineScene = "https://prod.spline.design/K1Bv-4yZUyv2b0Zd/scene.splinecode";
</script>

<svelte:head>
    <script type="module" src="https://unpkg.com/@splinetool/viewer@1.10.53/build/spline-viewer.js"></script>
    <link href="https://api.fontshare.com/v2/css?f[]=clash-display@200,300,400,500,600,700&display=swap" rel="stylesheet">
</svelte:head>

<!-- Global Spline Background - Fixed behind everything -->
<div class="global-spline-background">
    <spline-viewer 
        url={splineScene}
        events-target="global"
        class="global-spline">
    </spline-viewer>
</div>

<!-- All page content goes here -->
<main class="site-content">
    <slot />
</main>

<style>
    :global(*) {
        font-family: "Clash Display", sans-serif;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    :global(html), :global(body) {
        height: 100%;
        overflow-x: hidden;
    }

    :global(body) {
        background: transparent;
    }

    .global-spline-background {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        width: 100vw;
        height: 100vh;
        z-index: -1;
        pointer-events: none;
        user-select: none;
    }

    .global-spline, :global(spline-viewer) {
        width: 100%;
        height: 100%;
        display: block;
        border: none;
        pointer-events: auto;
        user-select: none;
    }
    
    :global(spline-viewer canvas) {
        pointer-events: auto;
    }

    .site-content {
        position: relative;
        z-index: 1;
        min-height: 100vh;
    }

    /* Ensure content is readable over 3D background */
    :global(.container) {
        position: relative;
        z-index: 2;
    }

    :global(h1), :global(h2), :global(h3) {
        text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
    }
</style>