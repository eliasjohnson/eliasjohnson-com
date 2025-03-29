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
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.1s; --direction: -100vw, 0;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>E</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.2s; --direction: 0, -100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>l</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.15s; --direction: 100vw, 0;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>i</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.25s; --direction: -100vw, -100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>a</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.3s; --direction: 0, 100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>s</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.35s; --direction: 0, 0;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>&nbsp;</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.4s; --direction: 100vw, 0;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>J</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.45s; --direction: 0, 100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>o</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.5s; --direction: -100vw, 0;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>h</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.55s; --direction: 0, -100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>n</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.6s; --direction: 100vw, 100vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>s</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.65s; --direction: -100vw, 50vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>o</span>
                    <span class="animate-letter" role="button" tabindex="0" style="--delay: 0.7s; --direction: 100vw, -50vh;" on:mouseenter={(e) => debouncedReanimateElement(e.currentTarget)}>n</span>
                </h1>
                <h2 class="subtitle">Front End Web Developer</h2>
            </div>
        </div>
    </section>

    <section id="experience" class="section">
        <div class="content">
            <h1 class="section-title" bind:this={experienceTitleEl}><span class="title-text scale-reveal" class:visible={sectionVisible.experience}>Experience</span><span class="comma">,</span></h1>
            <div class="experience-items">
                <div class="item-container">
                    <div class="experience-item" 
                        role="button"
                        tabindex="0"
                        class:active={activeExperienceItem === 'senior'}
                        on:mouseenter={() => showExperienceText('senior')}
                        on:mouseleave={hideExperienceText}
                        on:click={() => showExperienceText('senior')}
                        on:keydown={(e) => e.key === 'Enter' && showExperienceText('senior')}>
                        <h3>Information Technology Specialist</h3>
                        <p>Pattern | May 2023 - Present</p>
                        <p>Full-time hybrid position in Lehi, UT</p>
                    </div>
                    <div class="mobile-detail mobile-experience-senior" class:visible={experienceTextVisible && currentExperienceText === 'senior'}>
                        <ul>
                            <li>Delivered top-tier technical support, ranking as highest-performing ticket resolver for four consecutive quarters</li>
                            <li>Managed IT infrastructure and set up render farms, resulting in 4x faster render speeds</li>
                            <li>Reduced new-hire IT setup time by 66.7% while onboarding over 500 employees</li>
                            <li>Managed equipment inventory and worked with vendors to get the best deals</li>
                            <li>Created custom workflows with Tines and Python scripts utilizing APIs</li>
                        </ul>
                    </div>
                </div>
                
                <div class="item-container">
                    <div class="experience-item"
                        role="button"
                        tabindex="0"
                        class:active={activeExperienceItem === 'web'}
                        on:mouseenter={() => showExperienceText('web')}
                        on:mouseleave={hideExperienceText}
                        on:click={() => showExperienceText('web')}
                        on:keydown={(e) => e.key === 'Enter' && showExperienceText('web')}>
                        <h3>IT Support Engineer</h3>
                        <p>Microsoft | Sep 2021 - Apr 2023</p>
                        <p>Part-time remote position</p>
                    </div>
                    <div class="mobile-detail mobile-experience-web" class:visible={experienceTextVisible && currentExperienceText === 'web'}>
                        <ul>
                            <li>Provided comprehensive technical support to small and medium-sized businesses</li>
                            <li>Consistently ranked in top 5% for ticket resolutions and customer satisfaction</li>
                            <li>Effectively communicated with clients of all age groups and technical backgrounds</li>
                            <li>Leveraged expertise in Microsoft products to resolve complex technical issues</li>
                            <li>Collaborated with internal teams to ensure client satisfaction</li>
                        </ul>
                    </div>
                </div>
                
                <div class="item-container">
                    <div class="experience-item"
                        role="button"
                        tabindex="0"
                        class:active={activeExperienceItem === 'junior'}
                        on:mouseenter={() => showExperienceText('junior')}
                        on:mouseleave={hideExperienceText}
                        on:click={() => showExperienceText('junior')}
                        on:keydown={(e) => e.key === 'Enter' && showExperienceText('junior')}>
                        <h3>Web Developer</h3>
                        <p>Provo School of The Arts | Sep 2018 - Dec 2022</p>
                        <p>Freelance position in Provo, UT</p>
                    </div>
                    <div class="mobile-detail mobile-experience-junior" class:visible={experienceTextVisible && currentExperienceText === 'junior'}>
                        <ul>
                            <li>Designed and built the school's website from the ground up</li>
                            <li>Worked closely with the owner to create an effective online presence</li>
                            <li>Utilized Squarespace alongside custom code for optimal results</li>
                            <li>Created a website that effectively communicated the school's offerings and vision</li>
                            <li>Developed solutions targeting families and potential students</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div class="experience-detail" class:visible={experienceTextVisible} bind:this={experienceDetailEl}>
                {#if currentExperienceText === 'senior'}
                    <div class="experience-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
                        <ul>
                            <li>Delivered top-tier technical support, ranking as highest-performing ticket resolver for four consecutive quarters</li>
                            <li>Managed IT infrastructure and set up render farms, resulting in 4x faster render speeds</li>
                            <li>Reduced new-hire IT setup time by 66.7% while onboarding over 500 employees</li>
                            <li>Managed equipment inventory and worked with vendors to get the best deals</li>
                            <li>Created custom workflows with Tines and Python scripts utilizing APIs</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'web'}
                    <div class="experience-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
                        <ul>
                            <li>Provided comprehensive technical support to small and medium-sized businesses</li>
                            <li>Consistently ranked in top 5% for ticket resolutions and customer satisfaction</li>
                            <li>Effectively communicated with clients of all age groups and technical backgrounds</li>
                            <li>Leveraged expertise in Microsoft products to resolve complex technical issues</li>
                            <li>Collaborated with internal teams to ensure client satisfaction</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'junior'}
                    <div class="experience-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
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
                <div class="item-container">
                    <div class="education-item"
                        role="button"
                        tabindex="0"
                        class:active={activeEducationItem === 'bs'}
                        on:mouseenter={() => showEducationText('bs')}
                        on:mouseleave={hideEducationText}
                        on:click={() => showEducationText('bs')}
                        on:keydown={(e) => e.key === 'Enter' && showEducationText('bs')}>
                        <h3>B.S. Information Systems</h3>
                        <p>Utah Valley University | 2019 - 2024</p>
                        <p>Orem, UT</p>
                    </div>
                    <div class="mobile-detail mobile-education-bs" class:visible={educationTextVisible && currentEducationText === 'bs'}>
                        <ul>
                            <li>Database Theory - MySQL</li>
                            <li>Data Science; Big Data Analytics - Python & R</li>
                            <li>Data Warehousing - Microsoft SQL Server</li>
                            <li>Advanced Statistical Methods - R</li>
                            <li>Data Security Analytics - Kali Linux</li>
                            <li>Marketing & Organizational Behavior</li>
                            <li>Business Intelligence - Tableau</li>
                            <li>Business Communication</li>
                            <li>Financial and Managerial Accounting - Excel</li>
                            <li>Systems Design & Implementation - UML & Mermaid</li>
                            <li>Advanced Excel for Decision Making</li>
                            <li>Management Information Systems</li>
                            <li>Web Systems Development</li>
                        </ul>
                    </div>
                </div>
                
                <div class="item-container">
                    <div class="education-item"
                        role="button"
                        tabindex="0"
                        class:active={activeEducationItem === 'cs'}
                        on:mouseenter={() => showEducationText('cs')}
                        on:mouseleave={hideEducationText}
                        on:click={() => showEducationText('cs')}
                        on:keydown={(e) => e.key === 'Enter' && showEducationText('cs')}>
                        <h3>Computer Science</h3>
                        <p>Minor, Utah Valley University | 2019 - 2024</p>
                        <p>Orem, UT</p>
                    </div>
                    <div class="mobile-detail mobile-education-cs" class:visible={educationTextVisible && currentEducationText === 'cs'}>
                        <ul>
                            <li>Object Oriented Programming - Python</li>
                            <li>Data Structures & Algorithms - Python</li>
                            <li>Computer Networks - Wireshark</li>
                            <li>Linux Administration - Bash</li>
                            <li>Web Application Development - Full Stack</li>
                            <li>Computer Architecture - Assembly</li>
                            <li>Numerical Software Development - Python</li>
                        </ul>
                    </div>
                </div>
                
                <div class="item-container">
                    <div class="education-item"
                        role="button"
                        tabindex="0"
                        class:active={activeEducationItem === 'web'}
                        on:mouseenter={() => showEducationText('web')}
                        on:mouseleave={hideEducationText}
                        on:click={() => showEducationText('web')}
                        on:keydown={(e) => e.key === 'Enter' && showEducationText('web')}>
                        <h3>Web Development</h3>
                        <p>The Odin Project | 2024 - Present</p>
                        <p>Open Source Full Stack Development Course</p>
                    </div>
                    <div class="mobile-detail mobile-education-web" class:visible={educationTextVisible && currentEducationText === 'web'}>
                        <ul>
                            <li>Github & Git</li>
                            <li>HTML & CSS</li>
                            <li>Javascript</li>
                            <li>Svelte</li>
                            <li>React</li>
                            <li>Pnpm</li>
                            <li>Typescript</li>
                            <li>Web & UX Design</li>
                        </ul>
                    </div>
                </div>
            </div>
            
            <div class="education-detail" class:visible={educationTextVisible} bind:this={educationDetailEl}>
                {#if currentEducationText === 'bs'}
                    <div class="education-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
                        <ul>
                            <li>Database Theory - MySQL</li>
                            <li>Data Science; Big Data Analytics - Python & R</li>
                            <li>Data Warehousing - Microsoft SQL Server</li>
                            <li>Advanced Statistical Methods - R</li>
                            <li>Data Security Analytics - Kali Linux</li>
                            <li>Marketing & Organizational Behavior</li>
                            <li>Business Intelligence - Tableau</li>
                            <li>Business Communication</li>
                            <li>Financial and Managerial Accounting - Excel</li>
                            <li>Systems Design & Implementation - UML & Mermaid</li>
                            <li>Advanced Excel for Decision Making</li>
                            <li>Management Information Systems</li>
                            <li>Web Systems Development</li>
                        </ul>
                    </div>
                {:else if currentEducationText === 'cs'}
                    <div class="education-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
                        <ul>
                            <li>Object Oriented Programming - Python</li>
                            <li>Data Structures & Algorithms - Python</li>
                            <li>Computer Networks - Wireshark</li>
                            <li>Linux Administration - Bash</li>
                            <li>Web Application Development - Full Stack</li>
                            <li>Computer Architecture - Assembly</li>
                            <li>Numerical Software Development - Python</li>
                        </ul>
                    </div>
                {:else if currentEducationText === 'web'}
                    <div class="education-detail-content" in:fade={{duration: 200}} out:fade={{duration: 100}}>
                        <ul>
                            <li>Github & Git</li>
                            <li>HTML & CSS</li>
                            <li>Javascript</li>
                            <li>Svelte</li>
                            <li>React</li>
                            <li>Pnpm</li>
                            <li>Typescript</li>
                            <li>Web & UX Design</li>
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
                <div 
                    class="carousel-track" 
                    bind:this={carouselTrack}
                    role="presentation"
                    on:mouseenter={handleMouseEnter}
                    on:mouseleave={handleMouseLeave}
                >
                    <!-- First set of items -->
                    {#each projects as project}
                    <div 
                        class="project-item"
                        role="link"
                        tabindex="0"
                        on:click={() => window.open(project.link, '_blank')}
                        on:keydown={(e) => e.key === 'Enter' && window.open(project.link, '_blank')}
                    >
                        <div class="project-number">{project.number}</div>
                        <h3>{project.title}</h3>
                        {#if project.name}
                        <p class="project-name">{project.name}</p>
                        {/if}
                        <p>{project.description}</p>
                    </div>
                    {/each}
                    
                    <!-- Duplicate set for seamless loop -->
                    {#each projects as project}
                    <div 
                        class="project-item"
                        role="link"
                        tabindex="0"
                        on:click={() => window.open(project.link, '_blank')}
                        on:keydown={(e) => e.key === 'Enter' && window.open(project.link, '_blank')}
                    >
                        <div class="project-number">{project.number}</div>
                        <h3>{project.title}</h3>
                        {#if project.name}
                        <p class="project-name">{project.name}</p>
                        {/if}
                        <p>{project.description}</p>
                    </div>
                    {/each}
                </div>
            </div>
        </div>
    </section>

    <footer id="contact" class="footer">
        <div class="footer-content">
            <div class="footer-links">
                <a href="https://github.com/eliasjohnson" target="_blank" rel="noopener noreferrer" class="footer-link" aria-label="GitHub Profile">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
                </a>
                <a href="https://linkedin.com/in/eliasjohnson211" target="_blank" rel="noopener noreferrer" class="footer-link" aria-label="LinkedIn Profile">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
                </a>
                <a href="https://instagram.com/elias.hamke" target="_blank" rel="noopener noreferrer" class="footer-link" aria-label="Instagram Profile">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
                </a>
            </div>
            <div class="footer-text">© 2025 Elias Johnson</div>
        </div>
    </footer>
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
        align-items: flex-start;
        padding: 6rem 2rem 4rem;
        scroll-snap-align: start;
        overflow-y: auto;
        -webkit-overflow-scrolling: touch;
    }

    #home {
        align-items: center;
        justify-content: center;
        overflow-y: hidden;
    }

    #experience, #education, #projects {
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
    }

    #experience .content, #education .content {
        padding-bottom: 350px;
        margin-top: 0;
        padding-top: 2rem;
        transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
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
        will-change: transform, opacity; /* Optimize for animation */
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

    .experience-items, .education-items {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 2rem;
        margin-bottom: 2rem;
    }

    .experience-item, .education-item {
        padding: 1.5rem;
        padding-right: 3.5rem;
        border: 1px solid #eee;
        border-radius: 4px;
        transition: all 0.3s ease;
        position: relative;
        backface-visibility: hidden;
        transform: translateZ(0);
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        background-color: white;
        cursor: pointer;
    }

    .experience-item:hover, .education-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }

    .experience-item:hover h3, .education-item:hover h3 {
        color: olive;
    }

    .experience-item h3, .education-item h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        transition: color 0.3s ease;
    }

    .experience-item p, .education-item p {
        margin-bottom: 0.5rem;
        color: #666;
    }

    .experience-item p:last-child, .education-item p:last-child {
        margin-bottom: 0;
    }

    .experience-detail, .education-detail {
        width: 100%;
        height: 350px;
        overflow: hidden;
        transition: opacity 0.4s ease, visibility 0s 0.4s;
        opacity: 0;
        border-top: 1px solid #eee;
        margin-top: 1rem;
        visibility: hidden;
    }

    .experience-detail.visible, .education-detail.visible {
        opacity: 1;
        visibility: visible;
        transition: opacity 0.4s ease, visibility 0s;
    }

    .experience-detail-content, .education-detail-content {
        padding: 1.5rem 0;
    }

    .experience-detail ul, .education-detail ul {
        list-style-type: disc;
        padding-left: 1.5rem;
    }

    .experience-detail li, .education-detail li {
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

    .education-item:hover h3 {
        color: olive;
    }

    .education-item h3 {
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        transition: color 0.3s ease;
    }

    .education-item p {
        margin-bottom: 0.5rem;
        color: #666;
    }

    .item-container {
        position: relative;
    }

    .mobile-detail {
        display: none;
    }

    :global(html) {
        scroll-behavior: smooth;
        @media (min-width: 769px) {
            scroll-snap-type: y mandatory;
            overflow-y: scroll;
        }
    }

    :global(section) {
        min-height: 100vh;
        @media (min-width: 769px) {
            scroll-snap-align: start;
        }
    }

    .footer {
        padding: 4rem 2rem;
        background-color: #fff;
        position: relative;
        z-index: 10;
    }

    .footer-content {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 2rem;
    }

    .footer-links {
        display: flex;
        gap: 2rem;
        align-items: center;
    }

    .footer-link {
        color: #222;
        opacity: 0.6;
        transition: all 0.3s ease;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 0.5rem;
    }

    .footer-link:hover {
        opacity: 1;
        transform: translateY(-2px);
    }

    .footer-text {
        font-size: 0.875rem;
        color: #666;
        letter-spacing: 0.02em;
    }

    @media (max-width: 768px) {
        .footer {
            padding: 3rem 1.5rem;
        }

        .footer-content {
            gap: 1.5rem;
        }

        .footer-links {
            gap: 1.5rem;
        }
    }

    @media (max-width: 480px) {
        .footer {
            padding: 2rem 1rem;
        }

        .footer-content {
            gap: 1rem;
        }

        .footer-links {
            gap: 1.25rem;
        }

        .footer-text {
            font-size: 0.8125rem;
        }
    }

    #projects {
        min-height: auto;
        padding: 6rem 2rem 2rem;
        display: flex;
        align-items: flex-start;
        justify-content: flex-start;
    }

    #projects .content {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        width: 100%;
        padding-top: 2rem;
    }

    #projects .section-title {
        align-self: flex-start;
    }

    /* Performance optimizations */
    .carousel-track {
        transform: translateZ(0); /* Hardware acceleration */
        backface-visibility: hidden;
        perspective: 1000;
        will-change: transform;
    }

    .project-item {
        transform: translateZ(0); /* Hardware acceleration */
        backface-visibility: hidden;
        -webkit-font-smoothing: antialiased;
    }

    /* Reduce motion for users who prefer it */
    @media (prefers-reduced-motion: reduce) {
        .carousel-track {
            animation: none;
        }

        .project-item {
            transition: none;
        }
    }

    /* Ensure text remains readable */
    .project-item h3 {
        font-size: clamp(1.25rem, 4vw, 1.5rem);
        line-height: 1.3;
    }

    .project-item p {
        font-size: clamp(0.9rem, 3vw, 1rem);
        line-height: 1.5;
    }

    /* Optimize touch targets for mobile */
    @media (hover: none) and (pointer: coarse) {
        .project-item {
            min-height: 150px;
        }
    }

    .carousel-container {
        width: 100%;
        position: relative;
        overflow: hidden;
        padding: 2rem 0;
        margin-bottom: 2rem;
    }
    
    .carousel-track {
        display: grid;
        grid-auto-flow: column;
        grid-auto-columns: calc(33.333% - 1.334rem);
        gap: 2rem;
        padding: 0 2rem;
        transition: transform 0.5s ease;
        will-change: transform;
    }

    .project-item {
        padding: 2rem;
        border: 1px solid #eee;
        border-radius: 4px;
        background-color: white;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        cursor: pointer;
        height: 100%;
        display: flex;
        flex-direction: column;
    }

    .project-item:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.05);
    }

    @media (max-width: 1200px) {
        .carousel-track {
            grid-auto-columns: calc(50% - 1rem);
        }
    }

    @media (max-width: 768px) {
        #projects {
            padding: 4rem 1rem 2rem;
        }

        .carousel-track {
            grid-auto-columns: 85%;
            gap: 1rem;
            padding: 0 1rem;
        }

        .carousel-container {
            margin: 1rem -1rem;
            padding: 1rem 0;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
            scroll-snap-type: x mandatory;
        }

        .project-item {
            scroll-snap-align: center;
            padding: 1.5rem;
        }

        .experience-items, .education-items {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .item-container {
            display: flex;
            flex-direction: column;
            gap: 0;
            transition: gap 0.3s ease;
        }

        .experience-item, .education-item {
            border-radius: 4px;
            margin: 0;
            transition: all 0.3s ease;
        }

        .experience-item.active, .education-item.active {
            border-bottom-left-radius: 0;
            border-bottom-right-radius: 0;
            border-bottom: none;
        }

        .mobile-detail {
            display: block;
            max-height: 0;
            opacity: 0;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid transparent;
            border-top: none;
            border-bottom-left-radius: 4px;
            border-bottom-right-radius: 4px;
            background-color: white;
        }

        .mobile-detail.visible {
            max-height: none;
            opacity: 1;
            border-color: #eee;
            padding: 1.5rem;
        }

        .mobile-detail ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        .mobile-detail li {
            margin-bottom: 1rem;
            line-height: 1.6;
            color: #555;
            font-size: 0.95rem;
            position: relative;
            padding-left: 1.25rem;
        }

        .mobile-detail li:last-child {
            margin-bottom: 0;
        }

        .mobile-detail li::before {
            content: '•';
            position: absolute;
            left: 0;
            color: olive;
        }

        .experience-detail, .education-detail {
            display: none;
        }

        #experience .content, #education .content {
            padding-bottom: 2rem;
        }

        #projects {
            padding-bottom: 6rem;
            min-height: auto;
            height: auto;
        }

        #projects .content {
            padding-top: 1rem;
            margin-bottom: 2rem;
        }

        .footer {
            padding: 1.25rem 1rem;
            margin-top: 2rem;
        }
    }

    @media (min-width: 769px) {
        .experience-items, .education-items {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            width: 50%;
            position: relative;
            z-index: 2;
        }

        .item-container {
            width: 100%;
        }

        .experience-item, .education-item {
            width: 100%;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        .experience-detail, .education-detail {
            position: fixed;
            left: 55%;
            top: 50%;
            transform: translateY(-50%);
            width: 40%;
            height: auto;
            pointer-events: none;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.2s ease, visibility 0s;
            background: white;
            padding: 2rem;
            border: 1px solid #eee;
            border-radius: 4px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        .experience-detail.visible, .education-detail.visible {
            opacity: 1;
            visibility: visible;
            pointer-events: auto;
            transition: opacity 0.2s ease;
        }

        .experience-detail-content, .education-detail-content {
            padding: 0;
            height: auto;
        }

        .mobile-detail {
            display: none !important;
        }

        #experience .content, #education .content {
            padding-bottom: 2rem;
            position: relative;
            height: auto;
            min-height: auto;
            overflow: visible;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
        }

        /* Ensure sections have proper spacing */
        #experience, #education {
            min-height: 100vh;
            padding: 6rem 2rem;
            display: flex;
            align-items: center;
            overflow: visible;
        }

        .experience-item.active, .education-item.active {
            border-color: olive;
            transform: translateX(1rem);
        }
    }

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

    @media (max-width: 768px) {
        .navbar {
            padding: 1.25rem 1rem;
        }

        .nav-links {
            gap: 1.25rem;
        }

        .nav-item {
            font-size: 0.9rem;
            padding: 0.5rem 0;
        }

        .logo-text {
            font-size: 1.25rem;
        }
    }

    @media (max-width: 480px) {
        .navbar {
            padding: 1rem 0.75rem;
        }

        .nav-links {
            gap: 1rem;
        }

        .nav-item {
            font-size: 0.85rem;
        }

        #projects {
            padding: 3rem 0.75rem 2rem;
        }
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
    
    let experienceTitleEl: HTMLElement;
    let educationTitleEl: HTMLElement;
    let projectsTitleEl: HTMLElement;
    
    let sectionVisible = {
        experience: false,
        education: false,
        projects: false
    };
    
    let isHovering = false;
    let carouselTrack: HTMLElement | null = null;
    let autoplayInterval: number | null = null;
    let isScrolling: number;
    
    let activeExperienceItem = '';
    let activeEducationItem = '';
    
    let experienceDetailEl: HTMLElement;
    let educationDetailEl: HTMLElement;
    
    const projects = [
        {
            number: "01",
            title: "First Website",
            name: "About Elias Johnson",
            description: "My first website built with HTML and CSS, showcasing fundamental web development skills",
            link: "https://abouteliasjohnsoncss.netlify.app/",
            technologies: ["HTML", "CSS"]
        },
        {
            number: "02",
            title: "Student Registration",
            name: "Academic Portal",
            description: "Interactive student registration page with form validation and responsive design",
            link: "https://project5eliasjohnson.netlify.app/",
            technologies: ["HTML", "CSS", "JavaScript"]
        },
        {
            number: "03",
            title: "Book Database App",
            name: "Library Manager",
            description: "Dynamic book database application with search and filtering capabilities",
            link: "https://project4bookapp.netlify.app/",
            technologies: ["JavaScript", "CSS", "Web Storage API"]
        },
        {
            number: "04",
            title: "Trivia Web App",
            name: "Interactive Quiz Game",
            description: "Dynamic trivia application with multiple categories and score tracking",
            link: "https://eliasjohnsonproject3trivia.netlify.app/",
            technologies: ["JavaScript", "CSS", "API Integration"]
        },
        {
            number: "05",
            title: "Business Website",
            name: "Provo School of The Arts",
            description: "Website via Squarespace & IT infrastructure setup for a small business",
            link: "https://provoschoolofthearts.com/",
            technologies: ["Squarespace", "IT Infrastructure"]
        },
        {
            number: "06",
            title: "SAAS Onboarding Automations",
            name: "Pattern",
            description: "Automated employee onboarding for various SAAS platforms",
            link: "#",
            technologies: ["Automation", "SAAS"]
        },
        {
            number: "07",
            title: "Render Farm Management",
            name: "Pattern",
            description: "Deployed a Keyshot render farm for 300% faster rendering performance",
            link: "#",
            technologies: ["Keyshot", "Render Farm"]
        },
        {
            number: "08",
            title: "Custom Computer Builds",
            name: "Pattern",
            description: "I build custom computers for clients like Pattern and friends",
            link: "#",
            technologies: ["Hardware", "Custom Builds"]
        },
        {
            number: "09",
            title: "Eagle Scout Project",
            name: "BSOA",
            description: "Constructed an ATV bridge at Starvation Creek for the Utah Division of Wildlife Resources",
            link: "#",
            technologies: ["Project Management", "Construction"]
        },
        {
            number: "10",
            title: "This Website",
            name: "Personal",
            description: "Built this website with Svelte and Tailwind CSS, hosted on Github Pages",
            link: "#",
            technologies: ["Svelte", "Tailwind CSS", "GitHub Pages"]
        }
    ];
    
    function debounce(func: Function, wait: number) {
        let timeout: ReturnType<typeof setTimeout>;
        return function executedFunction(...args: any[]) {
            const later = () => {
                clearTimeout(timeout);
                func(...args);
            };
            clearTimeout(timeout);
            timeout = setTimeout(later, wait);
        };
    }
    
    const debouncedReanimateElement = debounce((element: HTMLElement) => {
        reanimateElement(element);
    }, 50);
    
    function reanimateElement(element: HTMLElement) {
        element.style.animation = 'none';
        element.style.opacity = '0';
        element.style.transform = `translate(${element.style.getPropertyValue('--direction')})`;
        
        element.getBoundingClientRect(); // Force reflow
        
        const delay = window.getComputedStyle(element).getPropertyValue('--delay');
        element.style.animation = `letterAppear 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards ${delay}`;
        
        setTimeout(() => {
            element.style.opacity = '1';
            element.style.transform = 'translate(0, 0)';
        }, 1200 + parseFloat(delay) * 1000);
    }
    
    function scrollToTop() {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    }
    
    function showExperienceText(type: string) {
        if (hideTimeout) {
            clearTimeout(hideTimeout);
            hideTimeout = null;
        }
        
        if (typeof window !== 'undefined' && window.innerWidth <= 768) {
            // Mobile behavior
            if (currentExperienceText === type && experienceTextVisible) {
                // If clicking the same item that's already open, close it
                experienceTextVisible = false;
                currentExperienceText = '';
                activeExperienceItem = '';
            } else {
                // Close any other open item and open the clicked one
                experienceTextVisible = true;
                currentExperienceText = type;
                activeExperienceItem = type;
            }
            return;
        }
        
        // Desktop behavior - update immediately
        activeExperienceItem = type;
        currentExperienceText = type;
        experienceTextVisible = true;
    }
    
    function hideExperienceText() {
        if (typeof window !== 'undefined' && window.innerWidth <= 768) return;
        experienceTextVisible = false;
        activeExperienceItem = '';
        document.getElementById('experience')?.classList.remove('has-detail-visible');
    }
    
    function showEducationText(type: string) {
        if (hideEducationTimeout) {
            clearTimeout(hideEducationTimeout);
            hideEducationTimeout = null;
        }
        
        if (typeof window !== 'undefined' && window.innerWidth <= 768) {
            // Mobile behavior
            if (currentEducationText === type && educationTextVisible) {
                // If clicking the same item that's already open, close it
                educationTextVisible = false;
                currentEducationText = '';
                activeEducationItem = '';
            } else {
                // Close any other open item and open the clicked one
                educationTextVisible = true;
                currentEducationText = type;
                activeEducationItem = type;
            }
            return;
        }
        
        // Desktop behavior - update immediately
        activeEducationItem = type;
        currentEducationText = type;
        educationTextVisible = true;
    }
    
    function hideEducationText() {
        if (typeof window !== 'undefined' && window.innerWidth <= 768) return;
        educationTextVisible = false;
        activeEducationItem = '';
        document.getElementById('education')?.classList.remove('has-detail-visible');
    }
    
    function handleMouseEnter() {
        isHovering = true;
        if (autoplayInterval) {
            clearInterval(autoplayInterval);
            autoplayInterval = null;
        }
    }

    function handleMouseLeave() {
        isHovering = false;
        if (window.innerWidth > 768) {
            startAutoplay();
        }
    }

    function startAutoplay() {
        if (autoplayInterval) {
            clearInterval(autoplayInterval);
        }
        autoplayInterval = setInterval(() => {
            if (!isHovering && carouselTrack && window.innerWidth > 768) {
                const container = carouselTrack.parentElement;
                if (container) {
                    const itemWidth = container.clientWidth * 0.33333 + 32;
                    const maxScroll = container.scrollWidth - container.clientWidth;
                    let newScrollLeft = container.scrollLeft + itemWidth;
                    
                    if (newScrollLeft > maxScroll) {
                        newScrollLeft = 0;
                    }
                    
                    container.scrollTo({
                        left: newScrollLeft,
                        behavior: 'smooth'
                    });
                }
            }
        }, 3000);
    }
    
    onMount(() => {
        const letters = document.querySelectorAll('.letter');
        letters.forEach(letter => {
            letter.addEventListener('animationend', () => {
                (letter as HTMLElement).style.opacity = '1';
                (letter as HTMLElement).style.transform = 'translate(0, 0)';
            }, { once: true });
        });
        
        const sections = document.querySelectorAll('.section');
        const navLinks = document.querySelectorAll('.nav-item');
        
        let currentSectionIndex = 0;
        let isScrolling = false;
        let lastScrollTime = 0;
        const scrollCooldown = 750;
        
        function updateActiveNavLink() {
            navLinks.forEach((link, index) => {
                if (index === currentSectionIndex) {
                    link.classList.add('active');
                } else {
                    link.classList.remove('active');
                }
            });
        }
        
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
            
            setTimeout(() => {
                isScrolling = false;
            }, 800);
        }
        
        function initializeSection() {
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
        
        function handleWheel(event: WheelEvent) {
            // Skip special scroll behavior on mobile devices
            if (window.innerWidth <= 768) return;
            
            if (isScrolling) {
                event.preventDefault();
                return;
            }
            
            const direction = event.deltaY > 0 ? 1 : -1;
            event.preventDefault();
            
            if (Math.abs(event.deltaY) > 10) {
                scrollToSection(currentSectionIndex + direction);
            }
        }
        
        function handleKeydown(event: KeyboardEvent) {
            // Skip special scroll behavior on mobile devices
            if (window.innerWidth <= 768) return;
            
            if (event.key === 'ArrowDown' || event.key === 'PageDown') {
                event.preventDefault();
                scrollToSection(currentSectionIndex + 1);
            } else if (event.key === 'ArrowUp' || event.key === 'PageUp') {
                event.preventDefault();
                scrollToSection(currentSectionIndex - 1);
            }
        }
        
        let touchStartY = 0;
        let touchEndY = 0;
        
        function handleTouchStart(e: TouchEvent) {
            // Skip special scroll behavior on mobile devices
            if (window.innerWidth <= 768) return;
            touchStartY = e.touches[0].clientY;
        }
        
        function handleTouchEnd(e: TouchEvent) {
            // Skip special scroll behavior on mobile devices
            if (window.innerWidth <= 768) return;
            
            touchEndY = e.changedTouches[0].clientY;
            const SWIPE_THRESHOLD = 50;
            
            if (Date.now() - lastScrollTime < scrollCooldown) return;
            
            if (touchStartY - touchEndY > SWIPE_THRESHOLD) {
                scrollToSection(currentSectionIndex + 1);
            } else if (touchEndY - touchStartY > SWIPE_THRESHOLD) {
                scrollToSection(currentSectionIndex - 1);
            }
        }
        
        function handleScroll() {
            // Skip special scroll behavior on mobile devices
            if (window.innerWidth <= 768) return;
            
            if (!isScrolling) {
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
        }
        
        const sectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const sectionId = entry.target.id;
                    if (sectionId in sectionVisible) {
                        sectionVisible[sectionId as keyof typeof sectionVisible] = true;
                    }
                }
            });
        }, {
            threshold: 0.3,
            rootMargin: "0px"
        });
        
        window.addEventListener('wheel', handleWheel, { passive: false });
        window.addEventListener('keydown', handleKeydown);
        window.addEventListener('scroll', handleScroll);
        window.addEventListener('touchstart', handleTouchStart, { passive: true });
        window.addEventListener('touchend', handleTouchEnd, { passive: true });
        
        navLinks.forEach((link, index) => {
            link.addEventListener('click', (event) => {
                event.preventDefault();
                scrollToSection(index);
            });
        });
        
        sections.forEach(section => {
            sectionObserver.observe(section);
        });
        
        initializeSection();
        
        // Initialize autoplay for desktop
        if (window.innerWidth > 768) {
            startAutoplay();
        }
        
        // Add touch handling for mobile carousel
        if (carouselTrack && typeof window !== 'undefined') {
            const container = carouselTrack.parentElement;
            if (container) {
                let isScrolling: number;
                
                container.addEventListener('scroll', () => {
                    window.clearTimeout(isScrolling);
                    isScrolling = window.setTimeout(() => {
                        const scrollLeft = container.scrollLeft;
                        const itemWidth = window.innerWidth <= 768 
                            ? container.clientWidth * 0.85 + 16  // Mobile: 85% width + gap
                            : window.innerWidth <= 1200
                                ? container.clientWidth * 0.5 + 32  // Tablet: 50% width + gap
                                : container.clientWidth * 0.33333 + 32;  // Desktop: 33.333% width + gap
                        
                        const nearestItem = Math.round(scrollLeft / itemWidth);
                        container.scrollTo({
                            left: nearestItem * itemWidth,
                            behavior: 'smooth'
                        });
                    }, 150);
                }, { passive: true });

                // Add mouse wheel horizontal scrolling for desktop
                container.addEventListener('wheel', (e: WheelEvent) => {
                    if (window.innerWidth > 768) {
                        e.preventDefault();
                        container.scrollLeft += e.deltaY;
                    }
                }, { passive: false });
            }
        }
        
        return () => {
            window.removeEventListener('wheel', handleWheel);
            window.removeEventListener('keydown', handleKeydown);
            window.removeEventListener('scroll', handleScroll);
            window.removeEventListener('touchstart', handleTouchStart);
            window.removeEventListener('touchend', handleTouchEnd);
            
            navLinks.forEach((link) => {
                link.removeEventListener('click', () => {});
            });
            
            if (sectionObserver) {
                sectionObserver.disconnect();
            }
            
            if (hideTimeout) clearTimeout(hideTimeout);
            if (hideEducationTimeout) clearTimeout(hideEducationTimeout);
        };
    });
</script>