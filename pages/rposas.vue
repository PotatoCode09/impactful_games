<template>
  <div class="min-h-screen bg-white flex justify-center items-center p-0">
    <div class="w-full max-w-2xl backdrop-blur-xl shadow-2xl card-container">
      <div class="card-border"></div>
      <div class="card-content">
        <div class="relative overflow-hidden header-section">
          <div class="absolute top-0 left-0 w-full h-full">
            <div class="absolute top-0 left-0 w-64 h-64 bg-purple-600 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob"></div>
            <div class="absolute top-0 right-0 w-64 h-64 bg-yellow-600 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob animation-delay-2000"></div>
            <div class="absolute -bottom-8 left-20 w-64 h-64 bg-pink-600 rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-blob animation-delay-4000"></div>
          </div>

          <div class="relative pt-16 pb-10 flex flex-col items-center text-center z-10">
            <div class="profile-container mb-6">
              <div class="profile-border"></div>
              <div class="glow"></div>
              <img
                src="/rposas.jpeg"
                alt="Rico Posas"
                class="profile-image relative z-10"
              />
            </div>
                  <div class="title-badge">
                    <div class="title-badge-border"></div>
                    <div class="title-badge-content font-Plus Jakarta Sans"> 
                      Rico Martin Carl V. Posas<br>
                      Brgy. Marcos Baybay City Leyte<br>
                      Creative Developer
                    </div>
                  </div>
            </div>
          </div>
        </div>

        <div class="content-section">
          <div class="space-y-8">
            <section class="transform-section bg-animate-section">
              <div class="section-content">
                <h2 class="section-heading mb-4">
                  <span class="section-icon"></span>
                  About Me
                </h2>
                <p class="font-semibold text-gray-300 leading-relaxed">
                  I'm a software developer focused on building accessible, performant
                  apps with Vue.js and Nuxt. I love clean design and scalable
                  architecture.
                </p>
              </div>
            </section>

            <section class="transform-section bg-animate-section">
              <div class="section-content">
                <h2 class="section-heading mb-4">
                  <span class="section-icon"></span>
                  Education
                </h2>
                <div class="pl-1">
                  <div class="flex items-center mb-1">
                    <span class="education-dot"></span>
                    <span class="font-semibold text-gray-200">Visayas State University</span>
                  </div>
                  <p class="ml-6 text-gray-300">Bachelor of Science in Computer Science</p>
                </div>
              </div>
            </section>

            <section class="transform-section bg-animate-section">
              <div class="section-content">
                <h2 class="section-heading mb-4">
                  <span class="section-icon"></span>
                  Skills
                </h2>
                <div class="flex flex-wrap gap-3 mt-2">
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-blue-500 to-indigo-600">Vue.js</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-green-500 to-emerald-600">Nuxt 3</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-yellow-500 to-amber-600">JavaScript</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-blue-500 to-cyan-600">TypeScript</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-purple-500 to-violet-600">C++</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-green-500 to-teal-600">Node.js</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-indigo-500 to-purple-600">C#</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-red-500 to-pink-600">Git</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-orange-500 to-amber-600">Python</span></div>
                  <div class="skill-wrapper"><span class="skill-tag bg-gradient-to-r from-blue-500 to-indigo-600">MySQL</span></div>
                </div>
              </div>
            </section>

            <section class="transform-section bg-animate-section">
              <div class="section-content">
                <h2 class="section-heading mb-4">
                  <span class="section-icon"></span>
                  Contact
                </h2>
                <div class="space-y-4">
                  <div class="contact-wrapper">
                    <div class="contact-border"></div>
                    <a href="mailto:ricoposas@gmail.com" class="contact-link">
                      <span class="contact-icon email-icon"></span>
                      ricoposas@gmail.com
                    </a>
                  </div>
                  <div class="contact-wrapper">
                    <div class="contact-border"></div>
                    <a href="https://github.com/Kissu1" target="_blank" class="contact-link">
                      <span class="contact-icon github-icon"></span>
                      github.com/Kissu1
                    </a>
                  </div>
                </div>
              </div>
            </section>
          </div>
        </div>
      </div>
    </div>
</template>

<style scoped>
body {
  font-family: 'Plus Jakarta Sans', system-ui, sans-serif;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  background-color: #000000;
}

.bg-white {
  background-color: #ffffff;
  margin: 0;
  padding: 0;
  width: 100%;
  max-width: 100vw;
}

.bg-animate-section {
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  border-radius: 12px;
  padding: 2px;
  transition: transform 0.3s ease;
  margin-bottom: 24px;
  overflow: hidden;
}

@keyframes gradient {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

.card-container {
  position: relative;
  border-radius: 0;
  padding: 0;
  background: black;
  overflow: hidden;
  width: 100%;
  max-width: 100%;
}

.card-border {
  position: absolute;
  inset: 0;
  border-radius: 0;
  border-width: 5px;
  padding: 0;
  animation: rotate 4s linear infinite;
}

.card-content {
  position: relative;
  z-index: 1;
  border-radius: 0;
  overflow: hidden;
}

.header-section {
  background:black;
}

.profile-container {
  position: relative; 
  left:8%; 
  margin-top: 20px;
  transform: translateX(-75px);
  width: 250px;
  height: 250px;
  padding: 5px;
}
.profile-border {
  position: absolute;
  inset: 0;
  border-radius: 50%;
  border-style: solid;
  border-width: 5px;
  padding: 4px;
  border-color:slategray;
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask-composite: exclude;
  animation: rotate 4s linear infinite;
  opacity: 0.9;
}

.profile-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  border: 2px solid rgba(255, 255, 255, 0.8);
  box-shadow: 0 0 25px rgba(0, 0, 0, 0.2);
}

.title-badge {
  position: relative;
  margin-left: 50px;
  margin-right: 1500px;
  margin-top: 8px;
  padding: 1px;
  border-radius: 1000px;
  overflow: hidden;
}

.title-badge-border {
  position: absolute;
  inset: 0;
  border-radius: 9999px;
  padding: 1px;
  background: white;
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask-composite: exclude;
  border-width: 5px;
  border-style:solid;
  border-color : slategray;
  ;
}

.title-badge-content {
  padding: 8px 18px;
  background: white;
  color: black;
  border-radius: 9999px;
  font-weight: 600;
  font-size: 1rem;
  font-style: italic;
  
}

.content-section {
  background: #000000;
  padding: 32px;
}

.transform-section {
  position: relative;
  transition: transform 0.3s ease;
}

.transform-section:hover {
  transform: translateY(-5px);
}

.section-content {
  background: #ffffff;
  border-radius: 10px;
  padding: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.section-heading {
  display: flex;
  align-items: center;
  font-size: 1.25rem;
  font-weight: 700;
  color: #111827;
  position: relative;
}

.section-icon {
  display: inline-block;
  width: 22px;
  height: 22px;
  margin-right: 10px;
  background: linear-gradient(to right, #f97316, #ec4899);
  border-radius: 6px;
  position: relative;
}

.section-icon::after {
  content: '';
  position: absolute;
  inset: 5px;
  background: #ffffff;
  border-radius: 2px;
}

.education-dot {
  width: 12px;
  height: 12px;
  background: linear-gradient(to right, #3b82f6, #8b5cf6);
  border-radius: 50%;
  margin-right: 8px;
  display: inline-block;
}

.skill-wrapper {
  position: relative;
  padding: 1px;
  border-radius: 20px;
  overflow: hidden;
  background: linear-gradient(
    60deg,
    rgba(99, 102, 241, 0.8) 0%,
    rgba(236, 72, 153, 0.8) 100%
  );
  transition: all 0.3s ease;
}

.skill-wrapper:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.15);
}

.skill-tag {
  padding: 8px 16px;
  border-radius: 19px;
  color: white;
  font-weight: 600;
  font-size: 0.875rem;
  display: block;
}

.contact-wrapper {
  position: relative;
  padding: 1px;
  border-radius: 10px;
  overflow: hidden;
}

.contact-border {
  position: absolute;
  inset: 0;
  border-radius: 10px;
  padding: 1px;
  background: linear-gradient(
    60deg,
    rgba(99, 102, 241, 0.6) 0%,
    rgba(139, 92, 246, 0.6) 100%
  );
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask-composite: exclude;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.contact-wrapper:hover .contact-border {
  opacity: 1;
}

.contact-link {
  display: flex;
  align-items: center;
  color: #111827;
  font-weight: 500;
  transition: all 0.3s ease;
  text-decoration: none;
  padding: 10px 12px;
  border-radius: 9px;
  background: #f3f4f6;
}

.contact-wrapper:hover .contact-link {
  transform: translateX(5px);
  background-color: #e5e7eb;
  color: #8b5cf6;
}

.contact-icon {
  width: 30px;
  height: 30px;
  border-radius: 8px;
  margin-right: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(to right, #6366f1, #8b5cf6);
  color: white;
  font-weight: bold;
  position: relative;
}

.email-icon::before {
  content: '@';
  color: white;
  font-size: 16px;
}

.github-icon::before {
  content: 'G';
  color: white;
  font-size: 16px;
}

@keyframes rotate {
  0% { background-position: 0% 50%; }
  100% { background-position: 100% 50%; }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}

@keyframes blob {
  0% { transform: translate(0px, 0px) scale(1); }
  33% { transform: translate(30px, -50px) scale(1.1); }
  66% { transform: translate(-20px, 20px) scale(0.9); }
  100% { transform: translate(0px, 0px) scale(1); }
}

@media (max-width: 640px) {
  .content-section {
    padding: 24px 20px;
  }

  .profile-container {
    width: 120px;
    height: 120px;
  }

  .section-content {
    padding: 16px;
  }

  .skill-tag {
    padding: 6px 12px;
    font-size: 0.8rem;
  }
}
</style>