<svelte:head>
    <title>Elias Johnson | Web Developer</title>
    <meta name="description" content="Information Technology Specialist and Front End Web Developer with experience at Pattern, Microsoft, and freelance projects">
    <meta property="og:title" content="Elias Johnson | Front End Web Developer">
    <meta property="og:description" content="IT specialist with expertise in technical support, infrastructure management, automation, and web development">
    <meta property="og:image" content="https://yourdomain.com/preview-image.jpg">
    <meta property="og:url" content="https://yourdomain.com">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
</svelte:head>

<!-- svelte-ignore css_unused_selector -->
<div class="container">
    <nav class="navbar">
        <div class="nav-logo">
            <a href="/" class="logo-text" on:click|preventDefault={scrollToTop}>3</a>
        </div>
        <ul class="nav-links">
            <li><a href="#home" class="nav-item">Home</a></li>
            <li><a href="#experience" class="nav-item">Experience</a></li>
            <li><a href="#education" class="nav-item">Education</a></li>
            <li><a href="#projects" class="nav-item">Projects</a></li>
        </ul>
    </nav>

    <section id="home" class="section">
        <div class="content">
            <div class="header">
                <h1 class="animated-title">
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.1s; --direction: -100vw, 0;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>E</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.2s; --direction: 0, -100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>l</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.15s; --direction: 100vw, 0;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>i</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.25s; --direction: -100vw, -100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>a</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.3s; --direction: 0, 100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>s</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.35s; --direction: 0, 0;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>&nbsp;</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.4s; --direction: 100vw, 0;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>J</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.45s; --direction: 0, 100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>o</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.5s; --direction: -100vw, 0;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>h</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.55s; --direction: 0, -100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>n</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.6s; --direction: 100vw, 100vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>s</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.65s; --direction: -100vw, 50vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>o</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.7s; --direction: 100vw, -50vh;" on:mouseenter={(e) => reanimateElement(e.currentTarget)}>n</span>
                </h1>
                <h2 class="subtitle">Front End Web Developer</h2>
            </div>
        </div>
    </section>

    <section id="experience" class="section">
        <div class="content">
            <h1 class="section-title" bind:this={experienceTitleEl}><span class="title-text scale-reveal" class:visible={sectionVisible.experience}>Experience</span><span class="comma">,</span></h1>
            <div class="experience-items">
                <div class="experience-item" 
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showExperienceText('senior')}
                    on:mouseleave={hideExperienceText}>
                    <h3>Information Technology Specialist</h3>
                    <p>Pattern | May 2023 - Present</p>
                    <p>Full-time hybrid position in Lehi, UT</p>
                </div>
                <div class="experience-item"
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showExperienceText('web')}
                    on:mouseleave={hideExperienceText}>
                    <h3>IT Support Engineer</h3>
                    <p>Microsoft | Sep 2021 - Apr 2023</p>
                    <p>Part-time remote position</p>
                </div>
                <div class="experience-item"
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showExperienceText('junior')}
                    on:mouseleave={hideExperienceText}>
                    <h3>Web Developer</h3>
                    <p>Provo School of The Arts | Sep 2018 - Dec 2022</p>
                    <p>Freelance position in Provo, UT</p>
                </div>
            </div>
            
            <div class="experience-detail" class:visible={experienceTextVisible}>
                {#if currentExperienceText === 'senior'}
                    <div class="experience-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Delivered top-tier technical support, ranking as highest-performing ticket resolver for four consecutive quarters</li>
                            <li>Managed IT infrastructure and set up render farms, resulting in 4x faster render speeds</li>
                            <li>Reduced new-hire IT setup time by 66.7% while onboarding over 500 employees</li>
                            <li>Automated SAAS employee onboardings via APIs</li>
                            <li>Created custom workflows with Tines and Python scripts utilizing APIs</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'web'}
                    <div class="experience-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Provided comprehensive technical support to small and medium-sized businesses</li>
                            <li>Consistently ranked in top 5% for ticket resolutions and customer satisfaction</li>
                            <li>Effectively communicated with clients of all age groups and technical backgrounds</li>
                            <li>Leveraged expertise in Microsoft products to resolve complex technical issues</li>
                            <li>Collaborated with internal teams to ensure client satisfaction</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'junior'}
                    <div class="experience-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Designed and built the school's website from the ground up</li>
                            <li>Worked closely with the owner to create an effective online presence</li>
                            <li>Utilized Squarespace alongside custom code for optimal results</li>
                            <li>Created a website that effectively communicated the school's offerings and vision</li>
                            <li>Developed solutions targeting families and potential students</li>
                        </ul>
                    </div>
                {/if}
            </div>
        </div>
    </section>

    <section id="education" class="section">
        <div class="content">
            <h1 class="section-title" bind:this={educationTitleEl}><span class="title-text scale-reveal" class:visible={sectionVisible.education}>Education</span><span class="comma">,</span></h1>
            <div class="education-items">
                <div class="education-item"
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showEducationText('bs')}
                    on:mouseleave={hideEducationText}>
                    <h3>B.S. Information Systems</h3>
                    <p>Utah Valley University | 2019 - 2024</p>
                    <p>Orem, UT</p>
                </div>
                <div class="education-item"
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showEducationText('cs')}
                    on:mouseleave={hideEducationText}>
                    <h3>Computer Science</h3>
                    <p>Minor, Utah Valley University | 2019 - 2024</p>
                    <p>Orem, UT</p>
                </div>
                <div class="education-item"
                    role="button"
                    tabindex="0"
                    on:mouseenter={() => showEducationText('web')}
                    on:mouseleave={hideEducationText}>
                    <h3>Web Development</h3>
                    <p>The Odin Project | 2024 - Present</p>
                    <p>Open Source Full Stack Development Course</p>
                </div>
            </div>
            
            <div class="education-detail" class:visible={educationTextVisible}>
                {#if currentEducationText === 'bs'}
                    <div class="education-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Database Theory - MySQL</li>
                            <li>Data Science - Python & R</li>
                            <li>Data Warehousing - Microsoft SQL Server</li>
                            <li>Advanced Statistical Methods - R</li>
                            <li>Data Security Analytics - Kali Linux</li>
                            <li>Marketing & Organizational Behavior</li>
                            <li>Business Intelligence - Tableau</li>
                            <li>Business Communication</li>
                            <li>Financial and Managerial Accounting</li>
                            <li>Systems Analysis and Design</li>
                        </ul>
                    </div>
                {:else if currentEducationText === 'cs'}
                    <div class="education-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Object Oriented Programming - Python</li>
                            <li>Data Structures and Algorithms - Python</li>
                            <li>Computer Networks - Wireshark</li>
                            <li>Linux Administration- Bash</li>
                            <li>Web Application Development - Full Stack</li>
                            <li>Computer Architecture - Assembly</li>
                        </ul>
                    </div>
                {:else if currentEducationText === 'web'}
                    <div class="education-detail-content" in:fade={{duration: 300, delay: 350}} out:fade={{duration: 200}}>
                        <ul>
                            <li>Github & Git</li>
                            <li>HTML & CSS</li>
                            <li>Javascript</li>
                            <li>Svelte</li>
                            <li>React</li>
                            <li>Pnpm</li>
                            <li>Typescript</li>
                            <li>Web and UX Design</li>
                        </ul>
                    </div>
                {/if}
            </div>
        </div>
    </section>

    <section id="projects" class="section">
        <div class="content">
            <h1 class="section-title" bind:this={projectsTitleEl}><span class="title-text scale-reveal" class:visible={sectionVisible.projects}>Projects</span><span class="comma">,</span></h1>
            <div class="carousel-container">
                <div class="carousel-track" bind:this={carouselTrack}>
                    {#each Array(3) as _}
                        <div class="project-item" 
                            role="link"
                            tabindex="0"
                            on:click={() => window.open('https://provoschoolofthearts.com/', '_blank')}
                            on:keydown={(e) => e.key === 'Enter' && window.open('https://provoschoolofthearts.com/', '_blank')}
                            style="cursor: pointer;">
                            <div class="project-number">01</div>
                            <h3>Business Website</h3>
                            <p class="project-name">Provo School of The Arts</p>
                            <p>Website via Squarespace & IT infrastructure setup for a small business</p>
                        </div>
                        <div class="project-item">
                            <div class="project-number">02</div>
                            <h3>SAAS Onboarding Automations</h3>
                            <p class="project-name">Pattern</p>
                            <p>Automated employee onboarding for various SAAS platforms</p>
                        </div>
                        <div class="project-item">
                            <div class="project-number">03</div>
                            <h3>Render Farm Management</h3>
                            <p class="project-name">Pattern</p>
                            <p>Deployed a Keyshot render farm for 300% faster rendering performance</p>
                        </div>
                        <div class="project-item">
                            <div class="project-number">04</div>
                            <h3>Custom Computer Builds</h3>
                            <p>I build custom computers for clients and friends</p>
                        </div>
                        <div class="project-item">
                            <div class="project-number">05</div>
                            <h3>Eagle Scout Project</h3>
                            <p class="project-name">BSOA</p>
                            <p>Contructed a bridge in at Starvation Creek for the Utah Division of Wildlife Resources</p>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </section>
</div>

<style>
    :global(*) {
        font-family: "Inter Tight", sans-serif;
        font-optical-sizing: auto;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    :global(html), :global(body) {
        overscroll-behavior: none; /* Prevent browser bounce effects */
        scroll-behavior: smooth;
    }

    :global(body) {
        overflow-y: scroll;
        background-color: #fff;
        color: #222;
    }

    .container {
        width: 100%;
        max-width: 100%;
        margin: 0 auto;
        position: relative;
    }
    
    .navbar {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 2rem;
        z-index: 100;
        background-color: rgba(255, 255, 255, 0.9);
        backdrop-filter: blur(5px);
    }
    
    .nav-logo {
        margin-right: auto;
    }
    
    .logo-text {
        font-weight: 700;
        font-size: 1.5rem;
        text-decoration: none;
        color: #000;
        transition: opacity 0.2s ease;
    }
    
    .logo-text:hover {
        opacity: 0.7;
    }

    .nav-links {
        display: flex;
        list-style: none;
        gap: 2rem;
    }

    .nav-item {
        text-decoration: none;
        color: #888;
        font-size: 1rem;
        font-weight: 500;
        transition: color 0.3s ease;
        position: relative;
    }
    .project-name {
        font-family: "Inter Tight", sans-serif;
        font-optical-sizing: auto;
        font-weight: 900;
        margin-bottom: 0.5rem;
        font-style: italic;
    }

    .nav-item::after {
        content: '';
        position: absolute;
        bottom: -5px;
        left: 0;
        width: 0;
        height: 2px;
        background-color: #000;
        transition: width 0.3s ease;
    }

    .nav-item:hover {
        color: #000;
    }
    
    .nav-item:hover::after {
        width: 100%;
    }

    .section {
        min-height: 100vh;
        width: 100%;
        display: flex;
        align-items: center;
        padding: 6rem 2rem 4rem;
        scroll-snap-align: start;
    }

    #experience, #education, #projects {
        display: flex;
        align-items: center;
    }

    #experience .content, #education .content {
        padding-bottom: 350px; /* Account for the hover detail content height */
        margin-top: 20%; /* Move content up to visually center it, accounting for the bottom padding */
    }

    .content {
        max-width: 1200px;
        width: 100%;
        margin: 0 auto;
    }

    .section-title {
        font-family: "Inter Tight", sans-serif;
        font-weight: 900;
        font-size: clamp(3rem, 10vw, 8rem);
        line-height: 1;
        margin-bottom: 3rem;
        color: #222;
    }
    
    .title-text {
        transition: color 0.3s ease;
        display: inline-block;
    }
    
    .title-text:hover {
        color: olive;
    }
    
    .section-title:hover {
        color: #222;
    }

    .comma {
        color: #222;
    }

    .header {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
    }

    .animated-title {
        font-family: "Inter Tight", sans-serif;
        font-optical-sizing: auto;
        font-weight: 900;
        font-style: normal;
        font-size: clamp(3rem, 10vw, 10rem);
        line-height: 1.1;
        margin-bottom: 1rem;
        display: flex;
        justify-content: flex-start;
    }
    
    .animate-letter {
        display: inline-block;
        opacity: 0;
        transform: translate(var(--direction, 0, 0));
        animation: letterAppear 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        animation-delay: var(--delay, 0s);
        cursor: pointer;
    }
    
    @keyframes letterAppear {
        0% {
            opacity: 0;
            transform: translate(var(--direction, 0, 0));
        }
        100% {
            opacity: 1;
            transform: translate(0, 0);
        }
    }

    .header h2 {
        font-weight: 700;
        font-size: clamp(2rem, 4vw, 3.5rem);
        opacity: 0;
        animation: fadeIn 0.8s ease forwards;
        animation-delay: 2s;
        margin-top: 0.5rem;
        font-style: italic;
        transition: color 0.3s ease, transform 0.3s ease;
        cursor: default;
    }
    
    .header h2:hover {
        color: olive;
        transform: scale(1.1);
    }

    @keyframes fadeIn {
        to { opacity: 0.9; }
    }

    .experience-items {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 2rem;
        margin-bottom: 2rem;
        position: relative;
    }

    .experience-item {
        padding: 1.5rem;
        border: 1px solid #eee;
        border-radius: 4px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        position: relative;
    }
    
    .experience-item::after {
        content: '';
        position: absolute;
        top: -15px;
        left: -15px;
        right: -15px;
        bottom: -15px;
        z-index: -1;
    }

    .experience-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }

    .experience-item:hover h3 {
        color: olive;
    }

    .experience-item h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        transition: color 0.3s ease;
    }

    .experience-item p {
        margin-bottom: 0.5rem;
        color: #666;
        transition: color 0.3s ease;
    }

    .carousel-container {
        width: 100vw;
        position: relative;
        overflow: hidden;
        padding: 2rem 0;
        margin-left: calc(-50vw + 50%);
        margin-right: calc(-50vw + 50%);
    }
    
    .carousel-track {
        display: flex;
        gap: 2rem;
        padding: 0 2rem;
        animation: slideTrack 67.5s linear infinite;
        width: max-content;
    }
    
    @keyframes slideTrack {
        0%, 4.4% {
            transform: translateX(0);
        }
        88%, 96% {
            transform: translateX(calc(-100% / 3 * 5/4)); /* Adjust for 5 items */
        }
        100% {
            transform: translateX(0);
        }
    }
    
    .project-item {
        flex: 0 0 calc((100vw - 8rem) / 3);
        min-width: 300px;
        padding: 1.5rem;
        border: 1px solid #eee;
        border-radius: 8px;
        background-color: white;
        box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        position: relative;
    }

    .project-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }

    .project-number {
        position: absolute;
        top: 1rem;
        right: 1rem;
        font-size: 2rem;
        font-weight: 900;
        color: #f0f0f0;
    }

    .project-item h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        padding-right: 3rem;
        transition: color 0.3s ease;
    }

    .project-item:hover h3 {
        color: olive;
    }

    .project-item p {
        color: #666;
    }

    @media (max-width: 768px) {
        .navbar {
            padding: 1rem;
        }
        
        .nav-links {
            gap: 1rem;
        }
        
        .section {
            padding: 5rem 1rem 3rem;
        }
        
        .experience-items{
            grid-template-columns: 1fr;
        }
        
        .project-item {
            flex: 0 0 calc(100vw - 4rem);
        }
        
        .carousel-track {
            gap: 1rem;
            padding: 0 1rem;
        }
        
        @keyframes slideTrack {
            0%, 4.4% {
                transform: translateX(0);
            }
            88%, 96% {
                transform: translateX(calc(-100% * 5/3)); /* Adjust for 5 items on mobile */
            }
            100% {
                transform: translateX(0);
            }
        }
    }

    /* Ensure text remains readable on very small screens */
    @media (max-width: 320px) {
        .header h1 {
            font-size: 2.5rem;
        }

        .header h2 {
            font-size: 1.2rem;
        }
        
        .section-title {
            font-size: 2rem;
        }
    }

    .experience-detail {
        width: 100%;
        height: 350px; /* Fixed height to prevent layout shift */
        overflow: hidden;
        transition: opacity 0.4s ease, visibility 0s 0.4s; /* Delay visibility change until after opacity fades */
        opacity: 0;
        border-top: 1px solid #eee;
        margin-top: 1rem;
        visibility: hidden; /* Hide it completely when not visible */
    }

    .experience-detail.visible {
        opacity: 1;
        visibility: visible; /* Show when visible */
        transition: opacity 0.4s ease, visibility 0s; /* No delay for visibility when showing */
    }
    
    .experience-detail-content {
        padding: 1.5rem 0;
    }
    
    .experience-detail ul {
        list-style-type: disc;
        padding-left: 1.5rem;
    }
    
    .experience-detail li {
        margin-bottom: 0.5rem;
        color: #555;
        line-height: 1.5;
    }

    .education-items {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 2rem;
        margin-bottom: 2rem;
    }

    .education-item {
        padding: 1.5rem;
        border: 1px solid #eee;
        border-radius: 4px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .education-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }

    .education-item h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        transition: color 0.3s ease;
    }

    .education-item:hover h3 {
        color: olive;
    }

    .education-item p {
        margin-bottom: 0.5rem;
        color: #666;
    }

    .education-detail {
        width: 100%;
        height: 350px; /* Fixed height to prevent layout shift */
        overflow: hidden;
        transition: opacity 0.4s ease, visibility 0s 0.4s; /* Delay visibility change until after opacity fades */
        opacity: 0;
        border-top: 1px solid #eee;
        margin-top: 1rem;
        visibility: hidden; /* Hide it completely when not visible */
    }

    .education-detail.visible {
        opacity: 1;
        visibility: visible; /* Show when visible */
        transition: opacity 0.4s ease, visibility 0s; /* No delay for visibility when showing */
    }
    
    .education-detail-content {
        padding: 1.5rem 0;
    }
    
    .education-detail ul {
        list-style-type: disc;
        padding-left: 1.5rem;
    }
    
    .education-detail li {
        margin-bottom: 0.5rem;
        color: #555;
        line-height: 1.5;
    }

    .scale-reveal {
        transform: scale(0.8);
        opacity: 0;
        transition: transform 0.8s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.8s cubic-bezier(0.16, 1, 0.3, 1);
        transform-origin: left center;
        display: inline-block;
    }
    
    .scale-reveal.visible {
        transform: scale(1);
        opacity: 1;
    }
</style>

<script lang="ts">
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';
    
    let experienceTextVisible = false;
    let currentExperienceText = '';
    let educationTextVisible = false;
    let currentEducationText = '';
    let hideTimeout: ReturnType<typeof setTimeout> | null = null;
    let hideEducationTimeout: ReturnType<typeof setTimeout> | null = null;
    
    // Add these variables for section animation
    let experienceTitleEl: HTMLElement;
    let educationTitleEl: HTMLElement;
    let projectsTitleEl: HTMLElement;
    
    let sectionVisible = {
        experience: false,
        education: false,
        projects: false
    };
    
    let carouselTrack: HTMLElement;
    let currentSlide = 0;
    let autoplayInterval: ReturnType<typeof setInterval>;
    
    function reanimateElement(element: HTMLElement) {
        // Reset the animation state
        element.style.animation = 'none';
        element.style.opacity = '0';
        element.style.transform = `translate(${element.style.getPropertyValue('--direction')})`;
        
        // Force reflow
        void element.offsetWidth;
        
        // Restart animation
        const delay = window.getComputedStyle(element).getPropertyValue('--delay');
        element.style.animation = `letterAppear 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards ${delay}`;
        
        // Safety fallback in case animation doesn't complete
        setTimeout(() => {
            element.style.opacity = '1';
            element.style.transform = 'translate(0, 0)';
        }, 1200 + parseFloat(delay) * 1000);
    }
    
    function scrollToTop(event: MouseEvent) {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    }
    
    function showExperienceText(type: string) {
        // Clear any pending hide timeout
        if (hideTimeout) {
            clearTimeout(hideTimeout);
            hideTimeout = null;
        }
        
        currentExperienceText = type;
        experienceTextVisible = true;
    }
    
    function hideExperienceText() {
        // Set opacity to 0 but keep the element visible during the transition
        experienceTextVisible = false;
        
        // No need for timeout as the CSS transition will handle the fade out
        if (hideTimeout) {
            clearTimeout(hideTimeout);
            hideTimeout = null;
        }
    }
    
    function showEducationText(type: string) {
        // Clear any pending hide timeout
        if (hideEducationTimeout) {
            clearTimeout(hideEducationTimeout);
            hideEducationTimeout = null;
        }
        
        currentEducationText = type;
        educationTextVisible = true;
    }
    
    function hideEducationText() {
        // Set opacity to 0 but keep the element visible during the transition
        educationTextVisible = false;
        
        // No need for timeout as the CSS transition will handle the fade out
        if (hideEducationTimeout) {
            clearTimeout(hideEducationTimeout);
            hideEducationTimeout = null;
        }
    }
    
    function updateCarousel() {
        // Not needed anymore
    }
    
    function nextSlide() {
        // Not needed anymore
    }
    
    function prevSlide() {
        // Not needed anymore
    }
    
    function goToSlide(index: number) {
        // Not needed anymore
    }
    
    onMount(() => {
        // Initialize animation for letters
        const letters = document.querySelectorAll('.letter');
        letters.forEach(letter => {
            // Ensure letters are visible after initial animation
            letter.addEventListener('animationend', () => {
                (letter as HTMLElement).style.opacity = '1';
                (letter as HTMLElement).style.transform = 'translate(0, 0)';
            }, { once: true });
        });
        
        // Get all sections and navigation links
        const sections = document.querySelectorAll('.section');
        const navLinks = document.querySelectorAll('.nav-item');
        
        let currentSectionIndex = 0;
        let isScrolling = false;
        let lastScrollTime = 0;
        const scrollCooldown = 750; // ms to wait between scroll actions
        
        // Update active navigation link
        function updateActiveNavLink() {
            navLinks.forEach((link, index) => {
                if (index === currentSectionIndex) {
                    link.classList.add('active');
                } else {
                    link.classList.remove('active');
                }
            });
        }
        
        // Scroll to section
        function scrollToSection(index: number) {
            if (index < 0 || index >= sections.length) return;
            
            const now = Date.now();
            if (now - lastScrollTime < scrollCooldown) return;
            
            lastScrollTime = now;
            isScrolling = true;
            currentSectionIndex = index;
            updateActiveNavLink();
            
            const target = sections[index] as HTMLElement;
            
            window.scrollTo({
                top: target.offsetTop,
                behavior: 'smooth'
            });
            
            // Reset scrolling state after animation completes
            setTimeout(() => {
                isScrolling = false;
            }, 800);
        }
        
        // Initialize - set starting section based on scroll position
        function initializeSection() {
            // Find closest section to current scroll position
            const scrollPosition = window.scrollY;
            let closestSection = 0;
            let closestDistance = Math.abs(sections[0].getBoundingClientRect().top);
            
            sections.forEach((section, index) => {
                const distance = Math.abs(section.getBoundingClientRect().top);
                if (distance < closestDistance) {
                    closestDistance = distance;
                    closestSection = index;
                }
            });
            
            currentSectionIndex = closestSection;
            updateActiveNavLink();
        }
        
        // Simple wheel handler
        function handleWheel(event: WheelEvent) {
            if (isScrolling) {
                event.preventDefault();
                return;
            }
            
            const direction = event.deltaY > 0 ? 1 : -1;
            event.preventDefault();
            
            // If significant scroll, move to next/prev section
            if (Math.abs(event.deltaY) > 10) {
                scrollToSection(currentSectionIndex + direction);
            }
        }
        
        // Handle navigation link clicks
        navLinks.forEach((link, index) => {
            link.addEventListener('click', (event) => {
                event.preventDefault();
                scrollToSection(index);
            });
        });
        
        // Handle keyboard navigation
        function handleKeydown(event: KeyboardEvent) {
            if (event.key === 'ArrowDown' || event.key === 'PageDown') {
                event.preventDefault();
                scrollToSection(currentSectionIndex + 1);
            } else if (event.key === 'ArrowUp' || event.key === 'PageUp') {
                event.preventDefault();
                scrollToSection(currentSectionIndex - 1);
            }
        }
        
        // Add event listeners
        window.addEventListener('wheel', handleWheel, { passive: false });
        window.addEventListener('keydown', handleKeydown);
        
        // Set initial section on page load
        initializeSection();
        
        // Update section highlight on manual scroll
        window.addEventListener('scroll', () => {
            if (!isScrolling) {
                // Find which section is most visible
                let maxVisibleSection = 0;
                let maxVisibleArea = 0;
                
                sections.forEach((section, index) => {
                    const rect = section.getBoundingClientRect();
                    const visibleHeight = Math.min(rect.bottom, window.innerHeight) - Math.max(rect.top, 0);
                    
                    if (visibleHeight > maxVisibleArea) {
                        maxVisibleArea = visibleHeight;
                        maxVisibleSection = index;
                    }
                });
                
                if (maxVisibleSection !== currentSectionIndex) {
                    currentSectionIndex = maxVisibleSection;
                    updateActiveNavLink();
                }
            }
        });

        // Set up intersection observers for section title animations
        const observerOptions = {
            threshold: 0.3, // When 30% of the section is visible
            rootMargin: "0px"
        };
        
        const sectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const sectionId = entry.target.id;
                    if (sectionId === 'experience') {
                        sectionVisible.experience = true;
                    } else if (sectionId === 'education') {
                        sectionVisible.education = true;
                    } else if (sectionId === 'projects') {
                        sectionVisible.projects = true;
                    }
                }
            });
        }, observerOptions);
        
        // Observe all sections
        document.querySelectorAll('.section').forEach(section => {
            sectionObserver.observe(section);
        });

        return () => {
            window.removeEventListener('wheel', handleWheel);
            window.removeEventListener('keydown', handleKeydown);
            window.removeEventListener('scroll', () => {});
            navLinks.forEach((link) => {
                link.removeEventListener('click', () => {});
            });
            sectionObserver.disconnect();
        };
    });
</script>