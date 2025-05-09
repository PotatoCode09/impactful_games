<template>
  <client-only>
    <NavBar />
    <main class="ig-main">
      <section class="portfolio-container">
        <div class="profile-column">
          <img src="/jamir.jpg" alt="Jamir Oasis M. Andrade" class="profile-img" />
        </div>
        <div class="content-column">
          <h1>Jamir Oasis M. Andrade</h1>
          <p class="subtitle">Junior SAP Developer, DXC Technology</p>
          <p class="contact">
            Ormoc City, PH • <a href="tel:+639510351575">+63 951 035 1575</a> •
            <a href="mailto:jamirandrade4270@gmail.com">jamirandrade4270@gmail.com</a>
          </p>

          <section>
            <h2>Experience</h2>
            <div>
              <h3>DXC Technology <span>Jul 2028 – Present</span></h3>
              <ul>
                <li>Reduced report generation time by 50% via system optimization.</li>
                <li>Built custom SAP modules to automate workflows (↓30% manual effort).</li>
                <li>Resolved 95% of issues within SLA windows.</li>
                <li>Improved DB response time by 5s via SQL tuning.</li>
              </ul>
            </div>
            <div>
              <h3>Lanex Philippines <span>Jan 2026 – Jun 2028</span></h3>
              <ul>
                <li>Maintained scalable apps; uptime ↑ to 90%.</li>
                <li>Built APIs; ↑ processing efficiency by 25%.</li>
                <li>Reduced page load time by 35%.</li>
              </ul>
            </div>
            <div>
              <h3>DXC Technology – Intern <span>May 2025 – Jun 2025</span></h3>
              <ul>
                <li>Improved delivery speed by 15%.</li>
                <li>Created tools to cut manual reporting by 20%.</li>
                <li>Enhanced SAP performance via ABAP and SQL.</li>
              </ul>
            </div>
          </section>

          <section>
            <h2>Projects</h2>
            <div>
                <h3>smartpay Ledger <span>Feb 2024 – Apr 2024</span></h3>
                <p>Engineered a lightweight transaction ledger app with SAP integration, enabling real-time financial tracking for SMEs.</p>
            </div>
            <div>
              <h3>auditify <span>Nov 2024 – Jan 2025</span></h3>
              <p>Built an internal auditing tool for SAP logs, enabling report automation and anomaly detection.</p>
            </div>
            <div>
              <h3>quickfill CRM <span>Jul 2024 – Oct 2024</span></h3>
              <p>Created a lightweight customer management app integrated with SAP backend systems for small teams.</p>
            </div>
          </section>

          <section>
            <h2>Certifications</h2>
            <ul>
              <li>SAP Certified ABAP Developer (2028)</li>
              <li>AWS Certified Developer – Associate (2027)</li>
            </ul>
          </section>

          <section>
            <h2>Skills</h2>
            <div class="skills">
              <span>Java</span><span>Python</span><span>ABAP</span><span>C++</span>
              <span>JavaScript</span><span>SQL</span><span>OOP</span><span>Agile</span>
              <span>Git</span><span>MySQL</span><span>Oracle</span><span>Azure</span>
              <span>AWS</span><span>SAP ABAP</span><span>API Dev</span><span>Debugging</span>
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
  title: 'Jamir Oasis M. Andrade',
  description: 'The personal page of Jamir Oasis M. Andrade.',
  charset: 'utf-8',
  viewport: 'width=device-width, initial-scale=1.0'
});

useHead({
  link: [
    { rel: 'icon', type: 'image/png', href: '/joystick.png' },
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
