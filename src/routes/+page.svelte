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
                <h2 class="subtitle">Software Engineer</h2>
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
                        class:active={activeExperienceItem === 'junior'}
                        on:mouseenter={() => showExperienceText('junior')}
                        on:mouseleave={hideExperienceText}
                        on:click={() => window.open('https://bookends.app', '_blank')}
                        on:keydown={(e) => e.key === 'Enter' && window.open('https://bookends.app', '_blank')}>
                        <h3>Software Engineer</h3>
                        <p>Bookends | Jan 2024 - Present</p>
                        <p>Freelance position in Provo, UT</p>
                    </div>
                    <div class="mobile-detail mobile-experience-junior" class:visible={experienceTextVisible && currentExperienceText === 'junior'}>
                        <ul>
                            <li>Helping with the development of a new product</li>
                            <li>Currently building an Epub reader and converter for IOS via Swift</li>
                            <li>Have learned a lot about Apple's ecosystem and development tools</li>
                        </ul>
                    </div>
                </div>

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
            </div>
            
            <div class="experience-detail" class:visible={experienceTextVisible} bind:this={experienceDetailEl}>
                {#if currentExperienceText === 'junior'}
                    <div class="experience-detail-content">
                        <ul>
                            <li>Helping with the development of a new product</li>
                            <li>Currently building an Epub reader and converter for IOS via Swift</li>
                            <li>Have learned a lot about Apple's ecosystem and development tools</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'senior'}
                    <div class="experience-detail-content">
                        <ul>
                            <li>Delivered top-tier technical support, ranking as highest-performing ticket resolver for four consecutive quarters</li>
                            <li>Managed IT infrastructure and set up render farms, resulting in 4x faster render speeds</li>
                            <li>Reduced new-hire IT setup time by 66.7% while onboarding over 500 employees</li>
                            <li>Managed equipment inventory and worked with vendors to get the best deals</li>
                            <li>Created custom workflows with Tines and Python scripts utilizing APIs</li>
                        </ul>
                    </div>
                {:else if currentExperienceText === 'web'}
                    <div class="experience-detail-content">
                        <ul>
                            <li>Provided comprehensive technical support to small and medium-sized businesses</li>
                            <li>Consistently ranked in top 5% for ticket resolutions and customer satisfaction</li>
                            <li>Effectively communicated with clients of all age groups and technical backgrounds</li>
                            <li>Leveraged expertise in Microsoft products to resolve complex technical issues</li>
                            <li>Collaborated with internal teams to ensure client satisfaction</li>
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
                    <div class="education-detail-content">
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
                    <div class="education-detail-content">
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
                    <div class="education-detail-content">
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
            <div class="bento-grid">
                <!-- Row 1: Bookends (large) + First Website + Student Registration -->
                <div class="bento-item large" data-project="bookends">
                    <a href="https://bookends.app" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">02</div>
                            <h3>Bookends</h3>
                            <p class="project-name">Reading habit builder</p>
                            <p class="project-description">I'm building out features and will soon be building a proprietary Epub reader into the app</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Swift</span>
                                <span class="tech-tag">iOS</span>
                                <span class="tech-tag">AWS Lambda</span>
                                <span class="tech-tag">DynamoDB</span>
                            </div>
                        </div>
                    </a>
                </div>

                <div class="bento-item small" data-project="first-website">
                    <a href="https://abouteliasjohnsoncss.netlify.app/" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">01</div>
                            <h3>First Website</h3>
                            <p class="project-name">About Elias Johnson</p>
                            <div class="project-technologies">
                                <span class="tech-tag">HTML</span>
                                <span class="tech-tag">CSS</span>
                            </div>
                        </div>
                    </a>
                </div>

                <div class="bento-item small" data-project="student-reg">
                    <a href="https://project5eliasjohnson.netlify.app/" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">03</div>
                            <h3>Student Registration</h3>
                            <p class="project-name">Academic Project</p>
                            <div class="project-technologies">
                                <span class="tech-tag">JavaScript</span>
                                <span class="tech-tag">CSS</span>
                            </div>
                        </div>
                    </a>
                </div>

                <!-- Row 2: Book Database + Trivia App -->
                <div class="bento-item small" data-project="book-db">
                    <a href="https://project4bookapp.netlify.app/" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">04</div>
                            <h3>Book Database</h3>
                            <p class="project-name">Library Manager</p>
                            <div class="project-technologies">
                                <span class="tech-tag">JavaScript</span>
                                <span class="tech-tag">API</span>
                            </div>
                        </div>
                    </a>
                </div>

                <div class="bento-item small" data-project="trivia">
                    <a href="https://eliasjohnsonproject3trivia.netlify.app/" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">05</div>
                            <h3>Trivia App</h3>
                            <p class="project-name">Interactive Quiz</p>
                            <div class="project-technologies">
                                <span class="tech-tag">JavaScript</span>
                                <span class="tech-tag">API</span>
                            </div>
                        </div>
                    </a>
                </div>

                <!-- Row 3: This Website (medium) + SAAS + Render Farm -->
                <div class="bento-item medium" data-project="this-website">
                    <span class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">11</div>
                            <h3>This Website</h3>
                            <p class="project-name">Personal</p>
                            <p class="project-description">Built with Svelte and modern web technologies</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Svelte</span>
                                <span class="tech-tag">TypeScript</span>
                                <span class="tech-tag">GitHub Pages</span>
                            </div>
                        </div>
                    </span>
                </div>

                <div class="bento-item small" data-project="saas">
                    <span class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">07</div>
                            <h3>SAAS Automations</h3>
                            <p class="project-name">Pattern</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Automation</span>
                                <span class="tech-tag">Python</span>
                            </div>
                        </div>
                    </span>
                </div>

                <div class="bento-item small" data-project="render-farm">
                    <span class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">08</div>
                            <h3>Render Farm</h3>
                            <p class="project-name">Pattern</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Keyshot</span>
                                <span class="tech-tag">Hardware</span>
                            </div>
                        </div>
                    </span>
                </div>

                <!-- Row 4: Custom Builds + Provo Arts + Eagle Scout (spans 2) -->
                <div class="bento-item small" data-project="custom-builds">
                    <span class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">09</div>
                            <h3>Custom Builds</h3>
                            <p class="project-name">Pattern</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Hardware</span>
                                <span class="tech-tag">Custom</span>
                            </div>
                        </div>
                    </span>
                </div>

                <div class="bento-item small" data-project="provo-arts">
                    <a href="https://provoschoolofthearts.com/" target="_blank" rel="noopener noreferrer" class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">06</div>
                            <h3>Provo Arts</h3>
                            <p class="project-name">Business Website</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Squarespace</span>
                                <span class="tech-tag">IT Setup</span>
                            </div>
                        </div>
                    </a>
                </div>

                <div class="bento-item medium" data-project="eagle-scout">
                    <span class="bento-link">
                        <div class="bento-content">
                            <div class="project-number">10</div>
                            <h3>Eagle Scout Project</h3>
                            <p class="project-name">BSOA</p>
                            <p class="project-description">Constructed an ATV bridge at Starvation Creek for the Utah Division of Wildlife Resources</p>
                            <div class="project-technologies">
                                <span class="tech-tag">Leadership</span>
                                <span class="tech-tag">Construction</span>
                                <span class="tech-tag">Project Management</span>
                            </div>
                        </div>
                    </span>
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

    :global(html) {
        scroll-behavior: smooth;
        overflow-y: scroll;
    }

    :global(html), :global(body) {
        overscroll-behavior: none; /* Prevent browser bounce effects */
        scroll-behavior: smooth;
        height: 100%;
    }

    :global(body) {
        overflow-y: auto;
        background-color: #fff;
        color: #222;
        scroll-snap-type: y proximity;
    }

    :global(#svelte) {
        height: 100%;
    }

    .container {
        width: 100%;
        max-width: 100%;
        margin: 0 auto;
        position: relative;
        height: 100%;
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
        height: 100vh;
        width: 100%;
        display: flex;
        align-items: flex-start;
        padding: 6rem 2rem 4rem;
        overflow-y: auto;
        -webkit-overflow-scrolling: touch;
    }

    #home {
        align-items: center;
        justify-content: center;
        overflow-y: hidden;
        scroll-snap-align: start;
    }

    #experience, #education {
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        scroll-snap-align: start;
    }

    #experience .content, #education .content {
        padding-bottom: 350px;
        margin-top: 0;
        padding-top: 2rem;
        transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
    }

    #projects {
        min-height: auto;
        height: auto;
        padding: 6rem 1rem 2rem;
        display: flex;
        align-items: flex-start;
        justify-content: flex-start;
        scroll-snap-align: none;
    }

    #projects .content {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        width: 100%;
        padding-top: 2rem;
        height: auto;
    }

    .footer {
        padding: 4rem 2rem;
        background-color: #fff;
        position: relative;
        z-index: 10;
        scroll-snap-align: none;
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

    .item-container {
        position: relative;
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
        transition: opacity 0.3s ease, visibility 0.3s ease;
        opacity: 0;
        border-top: 1px solid #eee;
        margin-top: 1rem;
        visibility: hidden;
    }

    .experience-detail.visible, .education-detail.visible {
        opacity: 1;
        visibility: visible;
        transition: opacity 0.3s ease, visibility 0s ease;
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

    .mobile-detail {
        display: none;
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

    .bento-grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: auto auto auto auto;
        gap: 1rem;
        width: 100%;
        max-width: 1200px;
        margin: 0 auto 4rem;
    }

    .bento-item {
        position: relative;
        border: 1px solid #2d4a2d;
        border-radius: 8px;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        overflow: hidden;
        color: white;
        min-height: 180px;
    }

    .bento-item:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 25px rgba(0,0,0,0.2);
    }

    .bento-item.large {
        grid-column: span 2;
        grid-row: span 2;
        background: linear-gradient(135deg, #1e3a1e 0%, #2d4a2d 100%);
    }

    .bento-item.medium {
        grid-column: span 2;
        grid-row: span 1;
    }

    .bento-item.small {
        grid-column: span 1;
        grid-row: span 1;
    }

    /* Individual project backgrounds */
    .bento-item[data-project="bookends"] {
        background: linear-gradient(135deg, #1e3a1e 0%, #2d4a2d 100%);
        border: 2px solid #4a6741;
    }

    .bento-item[data-project="first-website"] {
        background: linear-gradient(135deg, #2d4a2d 0%, #3a5a3a 100%);
    }

    .bento-item[data-project="this-website"] {
        background: linear-gradient(135deg, #3a5a3a 0%, #4a6741 100%);
    }

    .bento-item[data-project="student-reg"] {
        background: linear-gradient(135deg, #4a6741 0%, #5a7a52 100%);
    }

    .bento-item[data-project="book-db"] {
        background: linear-gradient(135deg, #2f5233 0%, #3f6242 100%);
    }

    .bento-item[data-project="trivia"] {
        background: linear-gradient(135deg, #3f6242 0%, #4f7252 100%);
    }

    .bento-item[data-project="provo-arts"] {
        background: linear-gradient(135deg, #2a4f2e 0%, #3a5f3e 100%);
    }

    .bento-item[data-project="saas"] {
        background: linear-gradient(135deg, #4f7252 0%, #5f8262 100%);
    }

    .bento-item[data-project="render-farm"] {
        background: linear-gradient(135deg, #3a5f3e 0%, #4a6f4e 100%);
    }

    .bento-item[data-project="custom-builds"] {
        background: linear-gradient(135deg, #5f8262 0%, #6f9272 100%);
    }

    .bento-item[data-project="eagle-scout"] {
        background: linear-gradient(135deg, #4a6f4e 0%, #5a7f5e 100%);
    }

    .bento-link {
        text-decoration: none;
        color: #222;
        display: block;
        height: 100%;
        width: 100%;
        transition: color 0.3s ease;
    }

    .bento-link:hover {
        color: #222;
    }

    .bento-content {
        padding: 1.25rem;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        position: relative;
    }

    .bento-item .project-number {
        font-family: "Inter Tight", sans-serif;
        font-weight: 700;
        font-size: 0.875rem;
        color: rgba(255, 255, 255, 0.7);
        margin-bottom: 0.5rem;
    }

    .bento-item h3 {
        font-size: 1.125rem;
        font-weight: 600;
        margin-bottom: 0.25rem;
        line-height: 1.3;
        color: #ffffff;
    }

    .bento-item .project-name {
        font-style: italic;
        font-weight: 500;
        font-size: 0.9rem;
        color: rgba(255, 255, 255, 0.8);
        margin-bottom: 0.5rem;
    }

    .bento-item .project-description {
        font-size: 0.85rem;
        color: rgba(255, 255, 255, 0.9);
        line-height: 1.4;
        margin-bottom: 1rem;
        flex-grow: 1;
    }

    .bento-item.large .project-description {
        font-size: 0.95rem;
        margin-bottom: 1.5rem;
    }

    .bento-item .project-technologies {
        display: flex;
        flex-wrap: wrap;
        gap: 0.375rem;
        margin-top: auto;
    }

    .bento-item .tech-tag {
        background-color: rgba(255, 255, 255, 0.15);
        color: #ffffff;
        padding: 0.125rem 0.5rem;
        border-radius: 6px;
        font-size: 0.75rem;
        font-weight: 500;
        white-space: nowrap;
        border: 1px solid rgba(255, 255, 255, 0.2);
    }

    .bento-item.large .tech-tag {
        font-size: 0.8rem;
        padding: 0.25rem 0.75rem;
    }

    .bento-item.large h3 {
        font-size: 1.5rem;
        color: #ffffff;
    }

    .bento-item.large .project-name {
        font-size: 1rem;
        color: rgba(255, 255, 255, 0.9);
    }

    @media (max-width: 768px) {
        #projects {
            padding: 4rem 1rem 4rem;
            min-height: auto;
        }

        .bento-grid {
            grid-template-columns: repeat(2, 1fr);
            grid-template-rows: repeat(7, 80px);
            gap: 0.75rem;
            width: 90vw;
            height: auto;
            aspect-ratio: auto;
        }

        .bento-item.large {
            grid-column: span 2;
            grid-row: span 2;
        }

        .bento-item.medium {
            grid-column: span 2;
            grid-row: span 1;
        }

        .bento-item.small {
            grid-column: span 1;
            grid-row: span 1;
        }

        .bento-content {
            padding: 1rem;
        }

        .bento-item h3 {
            font-size: 1rem;
        }

        .bento-item.large h3 {
            font-size: 1.25rem;
        }

        .bento-item .project-description {
            font-size: 0.8rem;
        }

        .bento-item .tech-tag {
            font-size: 0.7rem;
            padding: 0.125rem 0.375rem;
        }

        .experience-items, .education-items {
            display: flex;
            flex-direction: column;
            gap: 2rem;
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
    
    let hasAutoShownExperience = false;
    let hasAutoShownEducation = false;
    
    let activeExperienceItem = '';
    let activeEducationItem = '';
    
    let experienceDetailEl: HTMLElement;
    let educationDetailEl: HTMLElement;
    
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
        
        // Desktop behavior - smooth transition
        if (currentExperienceText === type && experienceTextVisible) {
            // Same item clicked, just keep it open
            return;
        }
        
        // If different item or first time, update smoothly
        activeExperienceItem = type;
        
        if (experienceTextVisible && currentExperienceText !== type) {
            // Fade out current, then fade in new
            experienceTextVisible = false;
            setTimeout(() => {
                currentExperienceText = type;
                experienceTextVisible = true;
            }, 150);
        } else {
            // First time showing or not currently visible
            currentExperienceText = type;
            experienceTextVisible = true;
        }
    }
    
    function hideExperienceText() {
        if (typeof window !== 'undefined' && window.innerWidth <= 768) return;
        
        hideTimeout = setTimeout(() => {
            experienceTextVisible = false;
            activeExperienceItem = '';
        }, 100);
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
        
        // Desktop behavior - smooth transition
        if (currentEducationText === type && educationTextVisible) {
            // Same item clicked, just keep it open
            return;
        }
        
        // If different item or first time, update smoothly
        activeEducationItem = type;
        
        if (educationTextVisible && currentEducationText !== type) {
            // Fade out current, then fade in new
            educationTextVisible = false;
            setTimeout(() => {
                currentEducationText = type;
                educationTextVisible = true;
            }, 150);
        } else {
            // First time showing or not currently visible
            currentEducationText = type;
            educationTextVisible = true;
        }
    }
    
    function hideEducationText() {
        if (typeof window !== 'undefined' && window.innerWidth <= 768) return;
        
        hideEducationTimeout = setTimeout(() => {
            educationTextVisible = false;
            activeEducationItem = '';
        }, 100);
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
            // Let CSS snap scroll handle everything
            return;
        }
        
        function handleKeydown(event: KeyboardEvent) {
            // Let CSS snap scroll handle everything
            return;
        }
        
        let touchStartY = 0;
        let touchEndY = 0;
        
        function handleTouchStart(e: TouchEvent) {
            // Let CSS snap scroll handle everything
            return;
        }
        
        function handleTouchEnd(e: TouchEvent) {
            // Let CSS snap scroll handle everything
            return;
        }
        
        function handleScroll() {
            // Let CSS snap scroll handle everything
            return;
        }
        
        const sectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                const sectionId = entry.target.id;
                
                if (entry.isIntersecting) {
                    if (sectionId in sectionVisible) {
                        sectionVisible[sectionId as keyof typeof sectionVisible] = true;
                        
                        // Auto-show first item details when section becomes visible
                        if (sectionId === 'experience' && !experienceTextVisible && !hasAutoShownExperience && !activeExperienceItem) {
                            setTimeout(() => {
                                if (!experienceTextVisible && !activeExperienceItem) { // Double check before showing
                                    showExperienceText('junior'); // Show first item (Software Engineer)
                                    hasAutoShownExperience = true;
                                }
                            }, 300);
                        } else if (sectionId === 'education' && !educationTextVisible && !hasAutoShownEducation && !activeEducationItem) {
                            setTimeout(() => {
                                if (!educationTextVisible && !activeEducationItem) { // Double check before showing
                                    showEducationText('bs'); // Show first item (B.S. Information Systems)
                                    hasAutoShownEducation = true;
                                }
                            }, 300);
                        }
                    }
                } else {
                    // Hide panels when leaving sections
                    if (sectionId === 'experience') {
                        experienceTextVisible = false;
                        activeExperienceItem = '';
                        currentExperienceText = '';
                    } else if (sectionId === 'education') {
                        educationTextVisible = false;
                        activeEducationItem = '';
                        currentEducationText = '';
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