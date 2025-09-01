<script lang="ts">
    import { onMount } from 'svelte';
    
    export let sceneId: string;
    export let className: string = '';

    let container: HTMLDivElement;

    onMount(() => {
        if (!container) return;

        // Create script tag for Spline web embed
        const script = document.createElement('script');
        script.type = 'module';
        script.src = 'https://unpkg.com/@splinetool/viewer@1.9.50/build/spline-viewer.js';
        
        script.onload = () => {
            // Create spline-viewer element
            const viewer = document.createElement('spline-viewer');
            viewer.setAttribute('url', `https://prod.spline.design/${sceneId}/scene.splinecode`);
            viewer.setAttribute('events-target', 'global');
            viewer.style.width = '100%';
            viewer.style.height = '100%';
            
            container.appendChild(viewer);
        };

        document.head.appendChild(script);

        return () => {
            if (script.parentNode) {
                script.parentNode.removeChild(script);
            }
        };
    });
</script>

<div bind:this={container} class="spline-web-embed {className}"></div>

<style>
    .spline-web-embed {
        width: 100%;
        height: 100%;
        position: relative;
    }
</style>