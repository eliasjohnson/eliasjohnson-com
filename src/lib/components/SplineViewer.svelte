<script lang="ts">
    import { onMount } from 'svelte';
    import { Application } from '@splinetool/runtime';

    export let scene: string;
    export let className: string = '';
    export let width: string = '100%';
    export let height: string = '400px';
    export let autoPlay: boolean = true;
    export let showControls: boolean = true;

    let canvas: HTMLCanvasElement;
    let spline: Application | null = null;
    let loading = true;
    let error = false;

    onMount(async () => {
        if (!canvas || !scene) return;

        try {
            spline = new Application(canvas);
            
            // Load the scene
            await spline.load(scene);
            
            // Configure scene settings after loading
            if (spline) {
                // Try to control autoplay
                if (!autoPlay) {
                    // Pause any animations
                    try {
                        spline.stop();
                    } catch (e) {
                        console.log('Could not control animations:', e);
                    }
                }
                
                // Set up interaction controls
                if (!showControls) {
                    // Disable camera controls if needed
                    canvas.style.pointerEvents = 'none';
                }
            }
            
            loading = false;
        } catch (err) {
            console.error('Failed to load Spline scene:', err);
            error = true;
            loading = false;
        }

        return () => {
            if (spline) {
                spline.dispose();
            }
        };
    });

    // Function to restart/reset the scene
    export function restartScene() {
        if (spline) {
            try {
                spline.stop();
                spline.play();
            } catch (e) {
                console.log('Could not restart scene:', e);
            }
        }
    }

    // Function to pause/play the scene
    export function togglePlayback() {
        if (spline) {
            try {
                if (autoPlay) {
                    spline.stop();
                    autoPlay = false;
                } else {
                    spline.play();
                    autoPlay = true;
                }
            } catch (e) {
                console.log('Could not toggle playback:', e);
            }
        }
    }
</script>

<div class="spline-container {className}" style="width: {width}; height: {height}">
    {#if loading && !error}
        <div class="spline-loader">
            <div class="spinner"></div>
            <p>Loading 3D scene...</p>
        </div>
    {/if}
    
    {#if error}
        <div class="spline-error">
            <p>Failed to load 3D scene</p>
        </div>
    {/if}
    
    <canvas 
        bind:this={canvas}
        class="spline-canvas"
        class:hidden={loading || error}
    ></canvas>
</div>

<style>
    .spline-container {
        position: relative;
        border-radius: 12px;
        overflow: hidden;
        background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
    }

    .spline-canvas {
        width: 100%;
        height: 100%;
        display: block;
        transition: opacity 0.3s ease;
    }

    .spline-canvas.hidden {
        opacity: 0;
        pointer-events: none;
    }

    .spline-loader {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        color: #666;
        z-index: 10;
    }

    .spline-error {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        text-align: center;
        color: #ef4444;
        z-index: 10;
    }

    .spinner {
        width: 40px;
        height: 40px;
        border: 3px solid #f3f3f3;
        border-top: 3px solid #666;
        border-radius: 50%;
        margin: 0 auto 1rem;
        animation: spin 1s linear infinite;
    }

    @keyframes spin {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
    }

    .spline-loader p, .spline-error p {
        font-family: "Clash Display", sans-serif;
        font-weight: 500;
        margin: 0;
    }
</style>