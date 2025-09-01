<script lang="ts">
    import { onMount } from 'svelte';
    import { base } from '$app/paths';
    
    let currentSlide = 0;
    let showLightbox = false;
    let lightboxImage = '';
    
    const slides = [
        { src: 'FS-1.jpeg', alt: 'IT Ticketing Dashboard - Overview' },
        { src: 'FS-2.jpeg', alt: 'IT Ticketing Dashboard - Ticket Details' },
        { src: 'FS-3.jpeg', alt: 'IT Ticketing Dashboard - Analytics' },
        { src: 'FS-4.png', alt: 'IT Ticketing Dashboard - Settings' }
    ];
    
    function nextSlide() {
        currentSlide = (currentSlide + 1) % slides.length;
    }
    
    function previousSlide() {
        currentSlide = (currentSlide - 1 + slides.length) % slides.length;
    }
    
    function goToSlide(index: number) {
        currentSlide = index;
    }
    
    function openLightbox() {
        lightboxImage = `${base}/${slides[currentSlide].src}`;
        showLightbox = true;
    }
    
    function closeLightbox() {
        showLightbox = false;
    }

    onMount(() => {
        const container = document.querySelector('.horizontal-container') as HTMLElement;
        
        if (!container) {
            console.error('Container not found');
            return;
        }
        
        // Enhanced wheel handler for both vertical and horizontal scrolling
        function handleScroll(event: WheelEvent) {
            if (!container) return;
            
            // Check if there's horizontal scrolling (from trackpad/horizontal wheel)
            if (Math.abs(event.deltaX) > Math.abs(event.deltaY)) {
                // Native horizontal scroll - let it through
                return;
            } else {
                // Convert vertical scroll to horizontal
                event.preventDefault();
                const scrollAmount = event.deltaY;
                container.scrollLeft += scrollAmount;
            }
        }
        
        // Add to container for better control
        container.addEventListener('wheel', handleScroll as EventListener, { passive: false });
        
        // Enhanced touch support for mobile
        let touchStartX = 0;
        let touchStartY = 0;
        let scrollStartX = 0;
        let isSwiping = false;
        
        function handleTouchStart(event: TouchEvent) {
            touchStartX = event.touches[0].clientX;
            touchStartY = event.touches[0].clientY;
            scrollStartX = container.scrollLeft;
            isSwiping = false;
        }
        
        function handleTouchMove(event: TouchEvent) {
            if (!touchStartX || !touchStartY) return;
            
            const touchEndX = event.touches[0].clientX;
            const touchEndY = event.touches[0].clientY;
            const diffX = touchStartX - touchEndX;
            const diffY = touchStartY - touchEndY;
            
            // Determine swipe direction early
            if (!isSwiping && (Math.abs(diffX) > 10 || Math.abs(diffY) > 10)) {
                isSwiping = true;
                // If horizontal swipe is greater than vertical, handle it
                if (Math.abs(diffX) > Math.abs(diffY)) {
                    event.preventDefault();
                }
            }
            
            // If we determined it's a horizontal swipe, handle scrolling
            if (isSwiping && Math.abs(diffX) > Math.abs(diffY)) {
                event.preventDefault();
                container.scrollLeft = scrollStartX + diffX;
            }
        }
        
        function handleTouchEnd() {
            touchStartX = 0;
            touchStartY = 0;
            scrollStartX = 0;
            isSwiping = false;
        }
        
        container.addEventListener('touchstart', handleTouchStart as EventListener, { passive: true });
        container.addEventListener('touchmove', handleTouchMove as EventListener, { passive: false });
        container.addEventListener('touchend', handleTouchEnd, { passive: true });
        
        // Arrow key navigation
        function handleKeydown(event: KeyboardEvent) {
            if (!container) return;
            switch(event.key) {
                case 'ArrowRight':
                    event.preventDefault();
                    container.scrollLeft += window.innerWidth;
                    break;
                case 'ArrowLeft':  
                    event.preventDefault();
                    container.scrollLeft -= window.innerWidth;
                    break;
                case 'ArrowDown':
                    event.preventDefault();
                    container.scrollLeft += window.innerWidth;
                    break;
                case 'ArrowUp':
                    event.preventDefault();  
                    container.scrollLeft -= window.innerWidth;
                    break;
            }
        }
        
        window.addEventListener('keydown', handleKeydown);
        
        // Cleanup
        return () => {
            container.removeEventListener('wheel', handleScroll as EventListener);
            container.removeEventListener('touchstart', handleTouchStart as EventListener);
            container.removeEventListener('touchmove', handleTouchMove as EventListener);
            container.removeEventListener('touchend', handleTouchEnd);
            window.removeEventListener('keydown', handleKeydown);
        };
    });
</script>

<svelte:head>
    <title>Elias Johnson | Software Engineer</title>
    <meta name="description" content="Software Engineer specializing in full-stack development and technical solutions">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <meta property="og:title" content="Elias Johnson | Software Engineer">
    <meta property="og:description" content="Software Engineer specializing in full-stack development and technical solutions">
    <meta property="og:image" content="https://yourdomain.com/preview-image.jpg">
    <meta property="og:url" content="https://yourdomain.com">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
</svelte:head>

<!-- Fixed Navigation -->
<nav class="navbar">
    <div class="social-links">
        <a href="https://github.com/eliasjohnson" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="GitHub Profile">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
        </a>
        <a href="https://linkedin.com/in/eliasjohnson211" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="LinkedIn Profile">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
        </a>
        <a href="https://linkedin.com/in/eliasjohnson211" target="_blank" class="contact-link">Get in touch</a>
    </div>
</nav>

<!-- Horizontal Scroll Container -->
<div class="horizontal-container">
    <!-- Section 1: Hero/Landing -->
    <section class="horizontal-section hero-section">
        <div class="section-content">
            <h1 class="name">Elias Johnson</h1>
            <h2>Software Engineer</h2>
            <div class="scroll-hint">
                <span class="scroll-text">Scroll horizontally →</span>
                <span class="scroll-text-mobile">Swipe to explore →</span>
                <div class="scroll-indicator">
                    <span>• • • • •</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 2: About -->
    <section class="horizontal-section about-section">
        <div class="section-content">
            <h2>About Me</h2>
            <p>As a Software Engineer and Data Analyst with a growth mindset, I lead with curiosity and thrive as a collaborative team player who learns quickly and welcomes new challenges. I leverage AI tools strategically—not just for speed, but to build smarter software that prioritizes user experience which brings real-world impact.</p>
            <p>Drawing from over 5 years in tech, I bring a plethora of skills, strong problem-solving abilities, and clear communication that allow me to think through complexities to deliver real, useful solutions.</p>
        </div>
    </section>

    <!-- Section 3: Skills -->
    <section class="horizontal-section skills-section">
        <div class="section-content">
            <h2>Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>AI & Development</h3>
                    <p>Cursor, Claude Code, Xcode</p>
                </div>
                <div class="skill-category">
                    <h3>Languages</h3>
                    <p>Python, JavaScript, TypeScript, Swift, Bash, Ruby, GO, Liquid</p>
                </div>
                <div class="skill-category">
                    <h3>Frameworks</h3>
                    <p>React, Svelte, NextJS, NodeJS, ROS </p>
                </div>
                <div class="skill-category">
                    <h3>Cloud & DevOps</h3>
                    <p>AWS, Azure, GCP, Vercel, Github Actions, Shopify CLI</p>
                </div>
                <div class="skill-category">
                    <h3>Databases & APIs</h3>
                    <p>MySQL, MCP, PostgreSQL, MongoDB, REST APIs, GraphQL, JSON handling</p>
                </div>
                <div class="skill-category">
                    <h3>Systems</h3>
                    <p>Linux, Windows, macOS, iOS</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 4: Experience -->
    <section class="horizontal-section experience-section">
        <div class="section-content">
            <h2>Current Experience</h2>
            <div class="experience-grid">
                <div class="experience-item">
                    <h3>Software Engineer</h3>
                    <h4>Bookends • Jan 2025 - Present</h4>
                    <p>Built and shipped core backend and frontend functionality for a native Swift reading habit tracker hosted on AWS. Supported growth to 100+ paid users.</p>
                </div>
                <div class="experience-item">
                    <h3>IT Systems Administrator</h3>
                    <h4>Pattern • May 2023 - Present</h4>
                    <p>Onboarded 1000+ employees with 67% reduction in setup time. Automated 154 hours of manual work annually via Python and Okta workflows.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 5: User Stories -->
    <section class="horizontal-section user-stories-section">
        <div class="section-content">
            <h2>Featured Work</h2>
            <p>IT Ticketing Dashboard - A comprehensive solution for managing and tracking IT support requests with real-time analytics and user-friendly interface.</p>
            
            <div class="carousel-container">
                <!-- Single image display with absolute positioning for each slide -->
                <div class="carousel-window" on:click={openLightbox} role="button" tabindex="0">
                    {#each slides as slide, index}
                        <img 
                            src="{base}/{slide.src}" 
                            alt={slide.alt}
                            class="carousel-image {index === currentSlide ? 'active' : ''}"
                            loading="eager"
                        />
                    {/each}
                    <div class="click-to-expand">Click to view full size</div>
                </div>
                
                <div class="carousel-nav">
                    <button class="carousel-btn prev-btn" on:click={previousSlide} aria-label="Previous image">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <polyline points="15,18 9,12 15,6"></polyline>
                        </svg>
                    </button>
                    <div class="carousel-indicators">
                        {#each slides as _, index}
                            <button 
                                class="indicator {index === currentSlide ? 'active' : ''}" 
                                on:click={() => goToSlide(index)} 
                                aria-label="Go to slide {index + 1}"
                            ></button>
                        {/each}
                    </div>
                    <button class="carousel-btn next-btn" on:click={nextSlide} aria-label="Next image">
                        <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <polyline points="9,18 15,12 9,6"></polyline>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
    </section>

    <!-- Section 6: Connect -->
    <section class="horizontal-section connect-section">
        <div class="section-content connect-content">
            <div class="connect-text">
                <h2>Let's Connect</h2>
                <p>Based in Salt Lake City, UT • Ready to build something amazing together? I'm always interested in exciting projects and new opportunities.</p>
                <div class="cta-buttons">
                    <a href="mailto:eliasjohnson211@gmail.com" class="cta-button">Email Me</a>
                    <a href="https://linkedin.com/in/eliasjohnson211" target="_blank" class="cta-button">LinkedIn</a>
                </div>
            </div>
            <div class="connect-portrait">
                <img src="{base}/me.jpeg" alt="Elias Johnson - Software Engineer" />
            </div>
        </div>
    </section>
</div>

<!-- Lightbox Modal -->
{#if showLightbox}
<div class="lightbox" on:click={closeLightbox}>
    <div class="lightbox-content">
        <img src={lightboxImage} alt="Full size view" />
        <button class="lightbox-close" on:click={closeLightbox} aria-label="Close lightbox">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <line x1="18" y1="6" x2="6" y2="18"></line>
                <line x1="6" y1="6" x2="18" y2="18"></line>
            </svg>
        </button>
    </div>
</div>
{/if}

<style>
    :global(html, body) {
        height: 100%;
        overflow: hidden;
        color: #222;
    }

    .navbar {
        position: fixed;
        top: 1rem;
        left: 50%;
        transform: translateX(-50%);
        width: auto;
        display: flex;
        align-items: center;
        padding: 0.5rem 0.75rem;
        z-index: 100;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(20px) saturate(180%);
        border-radius: 16px;
        border: 1px solid rgba(255, 255, 255, 0.2);
        box-shadow: 
            0 8px 32px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
    }
    
    .social-links {
        display: flex;
        align-items: center;
        gap: 0.5rem;
    }
    
    .social-link {
        color: #000;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 0.4rem;
        border-radius: 10px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px) saturate(180%);
        border: 1px solid rgba(255, 255, 255, 0.2);
        box-shadow: 
            0 2px 8px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
    }
    
    .social-link:hover {
        color: #000;
        background: rgba(255, 255, 255, 0.2);
        transform: translateY(-2px) scale(1.05);
        box-shadow: 
            0 4px 12px rgba(0, 0, 0, 0.1),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
        border-color: rgba(255, 255, 255, 0.3);
    }
    
    .contact-link {
        text-decoration: none;
        color: #000;
        font-size: 0.9rem;
        font-weight: 600;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        position: relative;
        padding: 0.4rem 0.8rem;
        margin-left: 0.5rem;
        border-radius: 10px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px) saturate(180%);
        border: 1px solid rgba(255, 255, 255, 0.2);
        box-shadow: 
            0 2px 8px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
    }

    .contact-link:hover {
        color: #000;
        background: rgba(255, 255, 255, 0.2);
        border-color: rgba(255, 255, 255, 0.3);
        transform: translateY(-2px);
        box-shadow: 
            0 4px 12px rgba(0, 0, 0, 0.1),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
    }

    /* Horizontal Scroll Container */
    .horizontal-container {
        display: flex;
        width: 100vw;
        height: 100vh;
        overflow-x: auto;
        overflow-y: hidden;
        scroll-behavior: smooth;
        scroll-snap-type: x mandatory;
        scrollbar-width: none; /* Firefox */
        -ms-overflow-style: none; /* IE and Edge */
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 10;
        background: transparent;
    }
    
    .horizontal-container::-webkit-scrollbar {
        display: none; /* Chrome, Safari and Opera */
    }

    .horizontal-section {
        width: 100vw;
        height: 100vh;
        flex-shrink: 0;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        scroll-snap-align: start;
        padding: 4rem 2rem 2rem;
    }

    .section-content {
        max-width: 800px;
        text-align: center;
        position: relative;
        z-index: 10;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(20px) saturate(180%);
        padding: 3rem;
        border-radius: 24px;
        box-shadow: 
            0 8px 32px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
        border: 1px solid rgba(255, 255, 255, 0.2);
        text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
    }

    /* Hero Section Styling */
    .hero-section .section-content {
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(20px) saturate(180%);
        border: 1px solid rgba(255, 255, 255, 0.1);
        box-shadow: 
            0 8px 32px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
    }

    .name {
        font-family: "Clash Display", sans-serif;
        font-weight: 800;
        font-size: clamp(2.5rem, 8vw, 6rem);
        line-height: 1.1;
        margin-bottom: 1rem;
        color: #000;
        white-space: nowrap;
    }

    .title {
        font-family: "Clash Display", sans-serif;
        font-weight: 600;
        font-size: clamp(4rem, 10vw, 8rem);
        color: #000;
        margin: 0 0 2rem 0;
    }

    .scroll-hint {
        opacity: 0.7;
        font-size: 1.1rem;
        color: #000;
        animation: pulse 2s infinite;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
    }

    .scroll-text {
        display: block;
    }

    .scroll-text-mobile {
        display: none;
    }

    .scroll-indicator {
        font-size: 1.5rem;
        letter-spacing: 0.5rem;
        opacity: 0.5;
        animation: slide 3s ease-in-out infinite;
    }

    @keyframes pulse {
        0%, 100% { opacity: 0.7; }
        50% { opacity: 1; }
    }
    
    @keyframes slide {
        0%, 100% { transform: translateX(0); }
        50% { transform: translateX(10px); }
    }

    /* Section Specific Styling */
    h2 {
        font-size: 2.5rem;
        font-weight: 700;
        margin-bottom: 1.5rem;
        color: #000;
    }

    .section-content p {
        font-size: 1.2rem;
        line-height: 1.6;
        color: #000;
        margin-bottom: 1.5rem;
    }

    .skills-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
        gap: 1.5rem;
        margin-top: 1.5rem;
    }

    .skill-category {
        text-align: center;
        padding: 0.75rem;
        background: rgba(255, 255, 255, 0.03);
        border-radius: 12px;
        border: 1px solid rgba(255, 255, 255, 0.08);
    }

    .skill-category h3 {
        font-size: 1.25rem;
        font-weight: 600;
        margin-bottom: 0.75rem;
        color: #000;
    }

    .skill-category p {
        font-size: 0.95rem;
        color: #000;
        line-height: 1.4;
    }

    .cta-buttons {
        display: flex;
        gap: 1rem;
        justify-content: center;
        margin-top: 2rem;
    }

    .cta-button {
        text-decoration: none;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(20px) saturate(180%);
        color: #000;
        padding: 1rem 2rem;
        border-radius: 16px;
        font-weight: 600;
        font-size: 1.1rem;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        box-shadow: 
            0 4px 16px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
        border: 1px solid rgba(255, 255, 255, 0.2);
    }

    .cta-button:hover {
        color: #000;
        background: rgba(255, 255, 255, 0.2);
        border-color: rgba(255, 255, 255, 0.3);
        transform: translateY(-2px);
        box-shadow: 
            0 8px 24px rgba(0, 0, 0, 0.1),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
    }

    /* Experience Section */
    .experience-grid {
        display: grid;
        gap: 2rem;
        margin-top: 2rem;
    }

    .experience-item {
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px) saturate(180%);
        padding: 1.5rem;
        border-radius: 16px;
        border: 1px solid rgba(255, 255, 255, 0.2);
        box-shadow: 
            0 4px 16px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
        text-align: left;
    }

    .experience-item h3 {
        font-size: 1.25rem;
        font-weight: 700;
        margin-bottom: 0.5rem;
        color: #000;
    }

    .experience-item h4 {
        font-size: 1rem;
        font-weight: 600;
        color: #000;
        margin-bottom: 1rem;
    }

    .experience-item p {
        font-size: 0.95rem;
        line-height: 1.5;
        color: #000;
        margin: 0;
    }

    /* Mobile Responsive */
    @media (max-width: 768px) {
        .navbar {
            top: 0.5rem;
            padding: 0.4rem 0.5rem;
            border-radius: 12px;
        }

        .horizontal-container {
            scroll-snap-type: x mandatory;
            -webkit-overflow-scrolling: touch;
        }

        .horizontal-section {
            padding: 3.5rem 1rem 1rem;
            scroll-snap-align: center;
        }

        .section-content {
            padding: 1.25rem;
            border-radius: 16px;
            max-width: 100%;
            width: 100%;
            box-sizing: border-box;
        }

        .name {
            font-size: clamp(2rem, 10vw, 3.5rem);
            word-break: break-word;
            white-space: normal;
        }

        .title {
            font-size: clamp(2.5rem, 8vw, 4rem);
        }

        h2 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .section-content p {
            font-size: 0.95rem;
            line-height: 1.4;
            margin-bottom: 1rem;
        }

        .skills-grid {
            grid-template-columns: 1fr 1fr;
            gap: 0.75rem;
            margin-top: 1rem;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            padding: 0.75rem;
            border-radius: 10px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .skill-category h3 {
            font-size: 1rem;
            margin-bottom: 0.5rem;
        }

        .skill-category p {
            font-size: 0.8rem;
            line-height: 1.3;
        }

        .experience-grid {
            gap: 1rem;
        }

        .experience-item {
            padding: 1.25rem;
        }

        .experience-item h3 {
            font-size: 1.1rem;
        }

        .experience-item h4 {
            font-size: 0.9rem;
        }

        .experience-item p {
            font-size: 0.85rem;
        }

        .connect-content {
            flex-direction: column;
            gap: 2rem;
            text-align: center;
        }

        .connect-portrait {
            flex: none;
        }

        .connect-portrait img {
            width: 220px;
            height: 220px;
        }

        .cta-buttons {
            flex-direction: column;
            align-items: stretch;
            width: 100%;
        }

        .cta-button {
            padding: 1rem 1.5rem;
            font-size: 1rem;
            width: 100%;
            text-align: center;
        }

        .social-links {
            gap: 0.25rem;
        }

        .social-link {
            padding: 0.35rem;
            border-radius: 8px;
            min-width: 32px;
            min-height: 32px;
        }

        .social-link svg {
            width: 16px;
            height: 16px;
        }

        .contact-link {
            font-size: 0.8rem;
            padding: 0.35rem 0.7rem;
            border-radius: 8px;
            margin-left: 0.3rem;
        }

        .scroll-hint {
            font-size: 0.9rem;
        }

        .scroll-text {
            display: none;
        }

        .scroll-text-mobile {
            display: block;
        }

        .scroll-indicator {
            font-size: 1.2rem;
        }
    }

    @media (max-width: 480px) {
        .navbar {
            padding: 0.35rem 0.4rem;
            top: 0.25rem;
        }

        .horizontal-section {
            padding: 2.75rem 0.5rem 0.5rem;
        }

        .section-content {
            padding: 1rem;
        }

        .name {
            font-size: clamp(1.75rem, 12vw, 3rem);
        }

        .title {
            font-size: clamp(2rem, 10vw, 3rem);
        }

        h2 {
            font-size: 1.25rem;
            margin-bottom: 0.75rem;
        }

        .section-content p {
            font-size: 0.85rem;
            line-height: 1.3;
            margin-bottom: 0.75rem;
        }

        .skills-grid {
            grid-template-columns: 1fr 1fr;
            gap: 0.5rem;
            margin-top: 0.75rem;
        }

        .skill-category {
            padding: 0.5rem;
            border-radius: 8px;
        }

        .skill-category h3 {
            font-size: 0.85rem;
            margin-bottom: 0.25rem;
            font-weight: 600;
        }

        .skill-category p {
            font-size: 0.7rem;
            line-height: 1.2;
        }

        .social-link {
            padding: 0.3rem;
            min-width: 28px;
            min-height: 28px;
        }

        .social-link svg {
            width: 14px;
            height: 14px;
        }

        .contact-link {
            font-size: 0.75rem;
            padding: 0.3rem 0.6rem;
        }

        .connect-portrait img {
            width: 180px;
            height: 180px;
        }
    }

    /* Carousel Styles */
    .carousel-container {
        position: relative;
        width: 100%;
        max-width: 600px;
        margin: 1.5rem auto 0;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px) saturate(180%);
        border-radius: 16px;
        border: 1px solid rgba(255, 255, 255, 0.2);
        box-shadow: 
            0 4px 16px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
        overflow: hidden;
    }

    .carousel-window {
        position: relative;
        height: 350px;
        overflow: hidden;
        cursor: pointer;
        background: rgba(0, 0, 0, 0.02);
    }

    .carousel-image {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: contain;
        opacity: 0;
        transition: opacity 0.3s ease;
    }

    .carousel-image.active {
        opacity: 1;
    }

    .click-to-expand {
        position: absolute;
        bottom: 10px;
        right: 10px;
        background: rgba(0, 0, 0, 0.7);
        color: white;
        padding: 0.25rem 0.5rem;
        border-radius: 6px;
        font-size: 0.75rem;
        opacity: 0;
        transition: opacity 0.3s ease;
        pointer-events: none;
    }

    .carousel-window:hover .click-to-expand {
        opacity: 1;
    }

    .carousel-nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        background: rgba(255, 255, 255, 0.05);
        backdrop-filter: blur(5px);
    }

    .carousel-btn {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 40px;
        height: 40px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px) saturate(180%);
        border: 1px solid rgba(255, 255, 255, 0.2);
        border-radius: 12px;
        color: #000;
        cursor: pointer;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        box-shadow: 
            0 2px 8px rgba(0, 0, 0, 0.05),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
    }

    .carousel-btn:hover {
        background: rgba(255, 255, 255, 0.2);
        border-color: rgba(255, 255, 255, 0.3);
        transform: translateY(-2px) scale(1.05);
        box-shadow: 
            0 4px 12px rgba(0, 0, 0, 0.1),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
    }

    .carousel-btn:active {
        transform: translateY(0) scale(0.95);
    }

    .carousel-indicators {
        display: flex;
        gap: 0.5rem;
        align-items: center;
    }

    .indicator {
        width: 10px;
        height: 10px;
        border-radius: 50%;
        border: 1px solid rgba(255, 255, 255, 0.3);
        background: rgba(255, 255, 255, 0.1);
        cursor: pointer;
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        backdrop-filter: blur(5px);
    }

    .indicator:hover {
        background: rgba(255, 255, 255, 0.2);
        border-color: rgba(255, 255, 255, 0.4);
        transform: scale(1.1);
    }

    .indicator.active {
        background: rgba(0, 0, 0, 0.6);
        border-color: rgba(0, 0, 0, 0.3);
        transform: scale(1.2);
    }

    /* Lightbox Styles */
    .lightbox {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.9);
        backdrop-filter: blur(10px);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 1000;
        animation: fadeIn 0.3s ease;
    }

    .lightbox-content {
        position: relative;
        max-width: 90vw;
        max-height: 90vh;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .lightbox-content img {
        max-width: 100%;
        max-height: 90vh;
        object-fit: contain;
        border-radius: 8px;
        animation: scaleIn 0.3s ease;
    }

    .lightbox-close {
        position: absolute;
        top: 20px;
        right: 20px;
        background: rgba(255, 255, 255, 0.1);
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255, 255, 255, 0.2);
        border-radius: 50%;
        width: 40px;
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        color: white;
        transition: all 0.3s ease;
    }

    .lightbox-close:hover {
        background: rgba(255, 255, 255, 0.2);
        transform: scale(1.1);
    }

    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }

    @keyframes scaleIn {
        from { transform: scale(0.9); opacity: 0; }
        to { transform: scale(1); opacity: 1; }
    }

    /* Mobile carousel adjustments */
    @media (max-width: 768px) {
        .carousel-container {
            margin: 1rem auto 0;
            max-width: 100%;
        }

        .carousel-window {
            height: 280px;
        }

        .carousel-nav {
            padding: 0.75rem;
        }

        .carousel-btn {
            width: 36px;
            height: 36px;
        }

        .carousel-btn svg {
            width: 16px;
            height: 16px;
        }

        .indicator {
            width: 8px;
            height: 8px;
        }
    }

    @media (max-width: 480px) {
        .carousel-container {
            margin: 1rem auto 0;
        }

        .carousel-window {
            height: 220px;
        }

        .carousel-nav {
            padding: 0.5rem;
        }

        .carousel-btn {
            width: 32px;
            height: 32px;
        }

        .carousel-btn svg {
            width: 14px;
            height: 14px;
        }

        .carousel-indicators {
            gap: 0.375rem;
        }

        .indicator {
            width: 6px;
            height: 6px;
        }
    }

    /* Connect Section Styles */
    .connect-content {
        display: flex;
        align-items: center;
        gap: 3rem;
        text-align: left;
    }

    .connect-text {
        flex: 1;
    }

    .connect-text h2 {
        text-align: center;
        margin-bottom: 1.5rem;
    }

    .connect-text p {
        text-align: center;
        margin-bottom: 2rem;
    }

    .connect-portrait {
        flex: 0 0 280px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .connect-portrait img {
        width: 280px;
        height: 280px;
        object-fit: cover;
        border-radius: 20px;
        background: rgba(255, 255, 255, 0.05);
        border: 2px solid rgba(255, 255, 255, 0.1);
        box-shadow: 
            0 8px 32px rgba(0, 0, 0, 0.1),
            inset 0 1px 0 rgba(255, 255, 255, 0.2);
        transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .connect-portrait img:hover {
        transform: translateY(-5px) scale(1.02);
        box-shadow: 
            0 12px 40px rgba(0, 0, 0, 0.15),
            inset 0 1px 0 rgba(255, 255, 255, 0.3);
        border-color: rgba(255, 255, 255, 0.2);
    }

    /* Improve touch scrolling on iOS */
    @supports (-webkit-touch-callout: none) {
        .horizontal-container {
            -webkit-overflow-scrolling: touch;
        }
    }
</style>