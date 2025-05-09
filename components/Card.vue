<template>
  <div class="designer-card">
    <!-- Top border dots -->
    <div class="border-dots top-dots">
      <div class="dot left-dot"></div>
      <div class="dot right-dot"></div>
    </div>

    <!-- Header text -->
    <div class="header-text">
      <h1>
        I handle everything from design to development — without endless
        meetings. Saving you time and headaches.
      </h1>
    </div>

    <!-- Work Experience Section -->
    <div class="section experience-section">
      <h2 class="section-title">Work Experience</h2>
      <div class="experience-grid">
        <div
          v-for="(job, idx) in workExperience"
          :key="idx"
          class="experience-item"
        >
          <div class="experience-header">
            <h3 class="company-name">{{ job.company }}</h3>
            <span class="job-duration">{{ job.period }}</span>
          </div>
          <div class="job-title">{{ job.title }}</div>
          <ul class="job-responsibilities">
            <li
              v-for="(responsibility, respIdx) in job.responsibilities"
              :key="respIdx"
            >
              {{ responsibility }}
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Education Section -->
    <div class="section education-section">
      <h2 class="section-title">Education</h2>
      <div class="education-item">
        <div class="education-header">
          <h3 class="university-name">{{ education.university }}</h3>
          <span class="education-duration">{{ education.period }}</span>
        </div>
        <div class="degree-info">{{ education.degree }}</div>
        <div class="honors">{{ education.honors }}</div>
      </div>
    </div>

    <!-- Projects Section -->
    <div class="section projects-section">
      <h2 class="section-title">Projects</h2>
      <div class="projects-grid">
        <div v-for="(project, idx) in projects" :key="idx" class="project-item">
          <h3 class="project-title">{{ project.title }}</h3>
          <div class="project-tech">{{ project.technologies }}</div>
          <p class="project-description">{{ project.description }}</p>
        </div>
      </div>
    </div>

    <!-- Skills Section -->
    <div class="section skills-section">
      <h2 class="section-title">Skills</h2>
      <div class="skills-grid">
        <div
          v-for="(skillCategory, idx) in skills"
          :key="idx"
          class="skill-category"
        >
          <div class="category-badge">
            <span
              class="category-dot"
              :class="`bg-${skillCategory.color}`"
            ></span>
            <span class="category-title">{{ skillCategory.title }}</span>
          </div>
          <div class="skills-list">
            <span
              v-for="(skill, skillIdx) in skillCategory.items"
              :key="skillIdx"
              class="skill-item"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>

    <!-- Bottom border dots -->
    <div class="border-dots bottom-dots">
      <div class="dot left-dot"></div>
      <div class="dot right-dot"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DesignerCard",
  props: {
    className: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      workExperience: [
        {
          company: "Tech Innovations Inc.",
          title: "Senior Full-Stack Developer",
          period: "2022 - Present",
          responsibilities: [
            "Led development of a SaaS platform with 200K+ users",
            "Architected microservices infrastructure using Node.js and Docker",
            "Mentored junior developers and implemented code review processes",
          ],
        },
        {
          company: "Digital Solutions Studio",
          title: "Frontend Developer",
          period: "2019 - 2022",
          responsibilities: [
            "Developed responsive web applications using Vue.js and React",
            "Improved website performance by 40% using code optimization techniques",
            "Collaborated with design team to implement pixel-perfect UI/UX",
          ],
        },
        {
          company: "WebCraft Agency",
          title: "Web Developer",
          period: "2017 - 2019",
          responsibilities: [
            "Built custom websites for clients across various industries",
            "Implemented SEO best practices resulting in improved rankings",
            "Created and maintained WordPress themes and plugins",
          ],
        },
      ],
      education: {
        university: "Visayas State University",
        degree: "Bachelor of Science in Computer Science",
        period: "2024 - 2028",
        honors: "Summa Cum Laude",
      },
      projects: [
        {
          title: "E-commerce Platform",
          technologies: "Vue.js, Node.js, MongoDB",
          description:
            "Built a fully-featured e-commerce platform with payment processing, inventory management, and analytics dashboard. Implemented real-time updates and notification system.",
        },
        {
          title: "Healthcare Management System",
          technologies: "React, Express, PostgreSQL",
          description:
            "Developed a HIPAA-compliant healthcare management system for scheduling, patient records, and billing. Integrated with third-party APIs for insurance verification.",
        },
        {
          title: "AI Content Generator",
          technologies: "Python, TensorFlow, React",
          description:
            "Created an AI-powered content generation tool that helps marketers create personalized content at scale. Implemented machine learning models for text generation and sentiment analysis.",
        },
      ],
      skills: [
        {
          title: "FRONTEND",
          color: "yellow",
          items: [
            "JavaScript/TypeScript",
            "React",
            "Vue.js",
            "Next.js",
            "HTML/CSS",
            "TailwindCSS",
            "Responsive Design",
          ],
        },
        {
          title: "BACKEND",
          color: "blue",
          items: [
            "Node.js",
            "Express",
            "Python",
            "Django",
            "RESTful APIs",
            "GraphQL",
            "Microservices",
          ],
        },
        {
          title: "DATABASE",
          color: "green",
          items: [
            "MongoDB",
            "PostgreSQL",
            "MySQL",
            "Redis",
            "Firebase",
            "ORM/ODM",
          ],
        },
        {
          title: "DEVOPS",
          color: "yellow",
          items: [
            "Docker",
            "Kubernetes",
            "CI/CD",
            "AWS",
            "Azure",
            "Git",
            "GitHub Actions",
          ],
        },
        {
          title: "OTHER",
          color: "blue",
          items: [
            "Agile/Scrum",
            "Performance Optimization",
            "Security Best Practices",
            "Testing (Jest, Mocha)",
            "Blockchain Development",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Dark theme variables */
:root {
  --background: #0e0e0e;
  --foreground: #ffffff;
  --border-color: #222222;
  --text-primary: #ffffff;
  --text-secondary: #888888;
  --dot-color: #555555;
  --highlight-yellow: #eab308;
  --highlight-blue: #3b82f6;
  --highlight-green: #22c55e;
}

.designer-card {
  width: 100%;
  max-width: 100%;
  margin: 0 auto;
  border-radius: 0;
  border: 1px solid var(--border-color);
  background-color: var(--background);
  color: var(--text-primary);
  overflow: hidden;
  font-family:
    -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu,
    Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
}

/* Border Dots */
.border-dots {
  position: relative;
  border-bottom: 1px solid var(--border-color);
  padding: 0.5rem 0;
}

.bottom-dots {
  border-bottom: none;
  border-top: 1px solid var(--border-color);
}

.dot {
  position: absolute;
  top: 50%;
  width: 0.5rem;
  height: 0.5rem;
  border-radius: 50%;
  background-color: var(--dot-color);
  transform: translateY(-50%);
}

.left-dot {
  left: 0.5rem;
}

.right-dot {
  right: 0.5rem;
}

/* Header Text */
.header-text {
  padding: 4rem 2rem;
  border-bottom: 1px solid var(--border-color);
  text-align: center;
}

.header-text h1 {
  font-size: 2.5rem;
  font-weight: 500;
  line-height: 1.2;
  margin: 0 auto;
  max-width: 950px;
  letter-spacing: -0.02em;
}

/* Content Section */
.content-section {
  padding: 2rem;
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
}

/* Bio Column */
.bio-column {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.bio-text {
  margin-bottom: 1.5rem;
}

.bio-text p {
  color: #888888;
  font-size: 1.125rem;
  line-height: 1.6;
  letter-spacing: 0.01em;
}

/* Services Column */
.services-column {
  display: grid;
  grid-gap: 2.5rem;
}

.service-category {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.category-header {
  display: flex;
  align-items: center;
}

.category-badge {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background-color: rgba(0, 0, 0, 0.4);
  padding: 0.5rem 1rem;
  border-radius: 2rem;
  width: fit-content;
}

.category-dot {
  display: inline-block;
  width: 0.75rem;
  height: 0.75rem;
  border-radius: 50%;
}

.bg-yellow {
  background-color: var(--highlight-yellow);
}

.bg-blue {
  background-color: var(--highlight-blue);
}

.bg-green {
  background-color: var(--highlight-green);
}

.category-title {
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-weight: 500;
  font-size: 0.875rem;
  color: var(--text-primary);
}

.category-items {
  display: grid;
  grid-template-columns: 1fr;
  gap: 0.75rem;
}

.service-item {
  color: var(--text-primary);
  font-weight: 400;
  font-size: 1.125rem;
  display: block;
  padding: 0.25rem 0;
}

/* Section Styling */
.section {
  padding: 3rem 4rem;
  border-top: 1px solid var(--border-color);
}

.section-title {
  font-size: 1.75rem;
  font-weight: 600;
  margin-bottom: 2rem;
  letter-spacing: -0.01em;
}

/* Work Experience Styling */
.experience-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2.5rem;
}

.experience-item {
  margin-bottom: 2rem;
}

.experience-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.company-name {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
}

.job-duration {
  color: var(--text-secondary);
  font-size: 0.875rem;
}

.job-title {
  font-size: 1.125rem;
  color: var(--highlight-yellow);
  margin-bottom: 1rem;
}

.job-responsibilities {
  list-style-type: disc;
  padding-left: 1.5rem;
  color: var(--text-secondary);
}

.job-responsibilities li {
  margin-bottom: 0.5rem;
  line-height: 1.5;
}

/* Education Styling */
.education-item {
  max-width: 600px;
}

.education-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.university-name {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--text-primary);
}

.education-duration {
  color: var(--text-secondary);
  font-size: 0.875rem;
}

.degree-info {
  font-size: 1.125rem;
  color: var(--highlight-blue);
  margin-bottom: 0.5rem;
}

.honors {
  font-size: 1rem;
  color: var(--highlight-yellow);
  font-style: italic;
}

/* Projects Styling */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2.5rem;
}

.project-item {
  border-left: 2px solid var(--highlight-green);
  padding-left: 1rem;
  padding-bottom: 1rem;
}

.project-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin-bottom: 0.5rem;
  color: var(--text-primary);
}

.project-tech {
  font-size: 0.875rem;
  color: var(--highlight-blue);
  margin-bottom: 1rem;
  font-weight: 500;
}

.project-description {
  color: var(--text-secondary);
  line-height: 1.6;
}

/* Skills Styling */
.skills-grid {
  display: grid;
  grid-gap: 2.5rem;
}

.skill-category {
  display: grid;
  grid-template-columns: 1fr 3fr;
  gap: 2rem;
  align-items: flex-start;
}

.skills-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 1rem;
}

.skill-item {
  background-color: rgba(255, 255, 255, 0.05);
  padding: 0.5rem 1rem;
  border-radius: 0.25rem;
  font-size: 0.9rem;
  display: inline-block;
}

/* Media Queries */
@media (min-width: 768px) {
  .header-text h1 {
    font-size: 3rem;
  }

  .content-section {
    padding: 3rem 4rem;
    grid-template-columns: 40% 60%;
    gap: 4rem;
  }

  .service-category {
    display: grid;
    grid-template-columns: 1fr 2fr;
    align-items: flex-start;
    gap: 1rem;
  }

  .category-items {
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
  }
}

@media (max-width: 768px) {
  .section {
    padding: 2rem;
  }

  .experience-grid,
  .projects-grid {
    grid-template-columns: 1fr;
  }

  .skill-category {
    grid-template-columns: 1fr;
  }

  .skills-list {
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  }
}
</style>
