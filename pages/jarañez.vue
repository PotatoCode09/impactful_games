<template>
  <div class="container">
    <div class="profile-header">
      <img src="/public/pat.png" alt="Profile Picture" class="profile-pic" />
      <div class="profile-info">
        <h1 class="name">John Patrick Y. Arañez</h1>
        <p class="email">johnaranez69@gmail.com</p>
        <p class="contact">Sta. Cruz St., Ormoc City, Leyte, Philippines</p>
        <p class="contact">09457126046</p>
      </div>
    </div>

    <section>
      <h2>Career Objective</h2>
      <p>
        To obtain employment as a Software Developer at Google Inc. where I can utilize my current skills, contribute to impactful systems, and grow into a world-class engineer.
      </p>
    </section>

    <section>
      <h2>Educational Background</h2>
      <div class="entry">
        <p><strong>Visayas State University</strong></p>
        <p>Bachelor of Science in Computer Science, Major in Software Technology</p>
        <p>2023 – 2028</p>
      </div>
    </section>

    <section>
      <h2>Work Experience</h2>
      <div class="entry">
        <p><strong>Junior Backend Developer</strong> | Networkz Technology Corporation | 2028 – Present</p>
        <p>Optimized database queries and microservices; reduced average API response times by 20%.</p>
      </div>
      <div class="entry">
        <p><strong>Software Engineering Intern</strong> | Bitcore Systems | 2027</p>
        <p>Built CLI automation tools using Node.js and developed internal APIs with Express and MongoDB.</p>
      </div>
      <div class="entry">
        <p><strong>DevOps Contributor</strong> | Freelance | 2026 – 2027</p>
        <p>Configured CI/CD pipelines with GitHub Actions & Docker for multiple small startups.</p>
      </div>
      <div class="entry">
        <p><strong>Full-Stack Developer</strong> | Side Hustle Studio | 2025 – 2026</p>
        <p>Developed full-blown web apps with Vue, Firebase, and TailwindCSS. Took on UX, testing, and deployment solo.</p>
      </div>
    </section>

    <section>
      <h2>Projects</h2>
      <div class="entry">
        <p><strong>diva.ai</strong> | 2024 – 2025</p>
        <p>Built an AI that mimics voices from short recordings. Deployed as a web app using Flask and React.</p>
      </div>
      <div class="entry">
        <p><strong>Paint Clone</strong> | 2025</p>
        <p>A Windows WPF app mimicking MS Paint with custom drawing tools, zoom, and layers.</p>
      </div>
      <div class="entry">
        <p><strong>osu! Stats Analyzer</strong> | 2026</p>
        <p>A tool that breaks down osu! replay files, tracking timing stats and consistency. Built with Python + Vue.</p>
      </div>
      <div class="entry">
        <p><strong>Budgetify</strong> | 2027</p>
        <p>Collaborative budgeting app with Firebase Auth, Firestore, and Vue. Let users track expenses in groups.</p>
      </div>
    </section>

    <section>
      <h2>Open Source Contributions</h2>
      <div class="entry">
        <p><strong>Nuxt.js</strong> — Fixed bug with dynamic routes in nested layouts</p>
        <p><strong>FreeCodeCamp</strong> — Contributed solutions & discussions to backend track</p>
        <p><strong>VSU Dev Guild Website</strong> — Helped launch student org website with responsive design</p>
      </div>
    </section>

    <section>
      <h2>Licenses and Certifications</h2>
      <div class="entry">
        <p><strong>AWS Certified Solutions Architect</strong></p>
        <p>Amazon Web Services (AWS)</p>
        <p>Oct 2019</p>
      </div>
    </section>

    <section>
      <h2>Skills</h2>
      <ul class="skills">
        <li>TypeScript</li>
        <li>Node.js</li>
        <li>Vue.js / Nuxt.js</li>
        <li>Firebase</li>
        <li>Python</li>
        <li>C++</li>
        <li>MongoDB</li>
        <li>MySQL</li>
        <li>Docker</li>
        <li>Git</li>
        <li>CI/CD (GitHub Actions)</li>
        <li>REST APIs</li>
        <li>HTML/CSS</li>
        <li>TailwindCSS</li>
        <li>Linux</li>
      </ul>
    </section>

    <section>
      <h2>Soft Skills</h2>
      <ul class="skills">
        <li>Strong Communication</li>
        <li>Problem Solving</li>
        <li>Team Collaboration</li>
        <li>Time Management</li>
        <li>Creative Thinking</li>
      </ul>
    </section>

    <section>
      <h2>Personal Interests</h2>
      <p>
        Outside work, I play rhythm games like osu! to keep my reflexes sharp, sketch digital art,
        and mess with game modding tools for fun. I also love cats, memes, and making unnecessarily
        complex Discord bots.
      </p>
    </section>
  </div>
</template>

<style scoped>
.container {
  max-width: 800px;
  margin: 2rem auto;
  padding: 1rem;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: #2c3e50;
  line-height: 1.6;
  background: #f9f9f9;
  border-radius: 12px;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);
}

.name {
  font-size: 1.8rem;
  font-weight: bold;
  margin-bottom: 0.2rem;
}

.email {
  font-size: 1rem;
  color: #3498db;
  margin-bottom: 0.2rem;
}

.contact {
  font-size: 0.9rem;
  color: #555;
}

section {
  margin-bottom: 2rem;
}

h2 {
  font-size: 1.4rem;
  color: #34495e;
  margin-bottom: 0.6rem;
  border-bottom: 1px solid #ccc;
  padding-bottom: 0.2rem;
}

.entry {
  margin-bottom: 1rem;
}

.skills {
  list-style-type: disc;
  padding-left: 1.2rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
  gap: 0.5rem;
}

.profile-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.profile-pic {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  border: 1px solid #ccc;
  object-fit: cover;
}

.profile-info {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
