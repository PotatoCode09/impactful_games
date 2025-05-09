<template>
    <client-only>
      <NavBar />
      <main class="ig-main">
        <section class="portfolio-container">
          <div class="profile-column">
            <img src="/jaaseia.png" alt="Jaaseia" class="profile-img" />
          </div>
          <div class="content-column">
            <h1>Jaaseia</h1>
            <p class="subtitle">Full Stack Developer</p>
            <p class="contact">
              Philippines • <a href="mailto:jaaseiacocabenoja@gmail.com">jaaseiacocabenoja@gmail.com</a> • 
              <a href="https://github.com/jaaseiadev" target="_blank">github.com/jaaseiadev</a>
            </p>
  
            <section>
              <h2>Experience</h2>
              <div>
                <h3>Programmer of the Year • <span>2024</span></h3>
                <ul>
                  <li>Awarded for exceptional coding performance in academic and competition settings.</li>
                </ul>
              </div>
              <div>
                <h3>Hackathon Champion • <span>Regional – 2024</span></h3>
                <ul>
                  <li>Led a team to victory with a working prototype for an e-commerce platform in under 48 hours.</li>
                </ul>
              </div>
            </section>
  
            <section>
              <h2>Projects</h2>
              <div>
                <h3>Gou Project <span>2025</span></h3>
                <p>A culturally inspired game built with a focus on storytelling, mechanics, and visual identity.</p>
              </div>
              <div>
                <h3>Student Data Management System</h3>
                <p>Created a MySQL-backed interface for managing and querying academic records efficiently.</p>
              </div>
            </section>
  
            <section>
              <h2>Skills</h2>
              <div class="skills">
                <span>HTML</span><span>CSS</span><span>JavaScript</span><span>Vue</span>
                <span>C</span><span>SQL</span><span>Assembly</span><span>Python</span>
                <span>MySQL</span><span>Node.js</span><span>Debugging</span><span>Game Dev</span>
              </div>
            </section>
          </div>
        </section>
      </main>
      <Copyright />
    </client-only>
  </template>
  
  <script setup lang="ts">
  import { useSeoMeta, useHead } from '@vueuse/head';
  import NavBar from '@/components/NavBar.vue';
  import Copyright from '@/components/Copyright.vue';
  
  useSeoMeta({
    title: 'Jaaseia – Portfolio',
    description: 'The personal portfolio of Jaaseia, aspiring full stack developer.',
    charset: 'utf-8',
    viewport: 'width=device-width, initial-scale=1.0'
  });
  
  useHead({
    link: [
      { rel: 'icon', type: 'image/png', href: '/icon.png' },
      { rel: 'stylesheet', href: '/reset.css' },
      { rel: 'stylesheet', href: '/custom.css' },
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css2?family=DM+Serif+Text:ital@0;1&display=swap'
      }
    ]
  });
  </script>
  
  <style scoped>
  .portfolio-container {
    display: flex;
    flex-direction: row;
    max-width: 1100px;
    margin: 80px auto;
    padding: 2rem;
    background: #fff;
    border-radius: 10px;
    border: 1px solid #ddd;
    font-family: 'DM Serif Text', serif;
    color: #333;
    gap: 40px;
  }
  .profile-column {
    flex: 0 0 200px;
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }
  .profile-img {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid #ccc;
  }
  .content-column {
    flex: 1;
  }
  h1 {
    font-size: 2em;
    margin-bottom: 0.2em;
  }
  .subtitle {
    font-size: 1.1em;
    color: #666;
  }
  .contact {
    font-size: 0.95em;
    margin-bottom: 1.5em;
  }
  .contact a {
    color: #FF6000;
    text-decoration: none;
  }
  .contact a:hover {
    text-decoration: underline;
  }
  h2 {
    font-size: 1.3em;
    margin-top: 2em;
  }
  h3 {
    margin-top: 1.2em;
    font-size: 1.05em;
    font-weight: 600;
  }
  h3 span {
    font-weight: normal;
    font-size: 0.9em;
    color: #777;
    margin-left: 10px;
  }
  ul {
    padding-left: 1.2em;
    margin-top: 0.5em;
  }
  ul li {
    margin-bottom: 0.5em;
    font-size: 0.95em;
  }
  .skills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 10px;
  }
  .skills span {
    background: #f0f0f0;
    padding: 6px 10px;
    border-radius: 20px;
    font-size: 0.85em;
  }
  </style>
  