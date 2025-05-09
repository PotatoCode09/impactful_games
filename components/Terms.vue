<template>
    <div class="terms-container">
      <div class="terms-content">
        <h1 class="terms-title">Kamotech Terms of Use</h1>
        <p class="effective-date">Effective as of: {{ currentDate }}</p>
        
        <!-- Table of Contents -->
        <div class="terms-nav">
          <a href="#introduction" class="nav-link">Introduction</a>
          <a href="#registration" class="nav-link">User Registration and Account</a>
          <a href="#rights" class="nav-link">User Rights and Consent</a>
          <a href="#data" class="nav-link">Data Collection and Use</a>
          <a href="#sharing" class="nav-link">Data Sharing</a>
          <a href="#security" class="nav-link">Data Security</a>
          <a href="#responsibilities" class="nav-link">User Responsibilities</a>
          <a href="#termination" class="nav-link">Termination of Account</a>
          <a href="#privacy" class="nav-link">Privacy Policy</a>
          <a href="#compliance" class="nav-link">Compliance with GDPR and Data Privacy Act</a>
          <a href="#changes" class="nav-link">Changes to Terms of Service</a>
          <a href="#contact" class="nav-link">Contact Us</a>
        </div>
  
        <!-- Sections -->
        <div id="introduction" class="terms-section">
          <h2 class="section-title">1. Introduction</h2>
          <p>Welcome to Kamotech, a game catalogue platform that allows users to browse, rate, comment, and interact with various video games across multiple genres. By using our platform, you agree to comply with these Terms of Service ("ToS"). If you do not agree, please do not use the platform.</p>
          <p>These ToS govern your access to and use of the platform and include provisions related to data privacy, as required under the General Data Protection Regulation (GDPR) and the Data Privacy Act of 2012.</p>
        </div>
  
        <div id="registration" class="terms-section">
          <h2 class="section-title">2. User Registration and Account</h2>
          <p>To access certain features (e.g., rating, commenting, and creating a wishlist), you must register and create an account. You agree to provide accurate and up-to-date information during the registration process and to update your information as necessary.</p>
          <p>We collect personal data such as your name, email address, and account preferences when you register. This data is necessary for providing our services, and we will handle it in accordance with applicable privacy laws, including the GDPR and the Data Privacy Act of 2012.</p>
        </div>
  
        <div id="rights" class="terms-section">
          <h2 class="section-title">3. User Rights and Consent</h2>
          <p>By creating an account, you consent to the collection and processing of your personal data as described in our Privacy Policy. You have the right to:</p>
          <ul class="terms-list">
            <li>Access, modify, and delete your personal data</li>
            <li>Withdraw consent at any time by contacting us</li>
            <li>Request that we stop processing your data for certain purposes, including marketing</li>
            <li>Object to any processing based on legitimate interests</li>
          </ul>
        </div>
  
        <div id="data" class="terms-section">
          <h2 class="section-title">4. Data Collection and Use</h2>
          <p>We collect personal data, including:</p>
          <ul class="terms-list">
            <li>Account Data: Name, email address, and profile information</li>
            <li>Interaction Data: Ratings, comments, and wishlist entries</li>
            <li>Technical Data: IP address, device information, and usage patterns</li>
          </ul>
          <p>We process this data to:</p>
          <ul class="terms-list">
            <li>Provide the platform's core features (e.g., game rating, comments, and wishlist)</li>
            <li>Improve our services and user experience</li>
            <li>Communicate with users about updates and relevant features</li>
            <li>Comply with legal obligations and user requests</li>
          </ul>
        </div>
  
        <div id="sharing" class="terms-section">
          <h2 class="section-title">5. Data Sharing</h2>
          <p>We do not share your personal data with third parties except in the following circumstances:</p>
          <ul class="terms-list">
            <li>With service providers who assist us in operating the platform</li>
            <li>When required by law, regulation, or legal process</li>
            <li>In the event of a business transfer, such as a merger or acquisition</li>
          </ul>
        </div>
  
        <div id="security" class="terms-section">
          <h2 class="section-title">6. Data Security</h2>
          <p>We take reasonable measures to protect your personal data from unauthorized access, loss, or alteration. However, no data transmission over the internet is 100% secure. By using the platform, you acknowledge the inherent risks associated with online data transmission.</p>
        </div>
  
        <div id="responsibilities" class="terms-section">
          <h2 class="section-title">7. User Responsibilities</h2>
          <p>You are responsible for maintaining the confidentiality of your account credentials and for any activity conducted under your account. You agree not to engage in:</p>
          <ul class="terms-list">
            <li>Posting illegal, harmful, or offensive content</li>
            <li>Violating the rights of other users, including harassment or spamming</li>
            <li>Using the platform for unauthorized or unlawful purposes</li>
          </ul>
        </div>
  
        <div id="termination" class="terms-section">
          <h2 class="section-title">8. Termination of Account</h2>
          <p>We may suspend or terminate your account if you violate these ToS. You may also request to delete your account at any time. Upon account deletion, we will retain your data only as required by law.</p>
        </div>
  
        <div id="privacy" class="terms-section">
          <h2 class="section-title">9. Privacy Policy</h2>
          <p>For more detailed information about how we collect, use, and protect your personal data, please refer to our Privacy Policy.</p>
        </div>
  
        <div id="compliance" class="terms-section">
          <h2 class="section-title">10. Compliance with GDPR and Data Privacy Act of 2012</h2>
          <p>If you are a resident of the European Union, your personal data is processed in accordance with the General Data Protection Regulation (GDPR). You have the right to request access to, correction of, or deletion of your personal data, and the right to object to processing.</p>
          <p>If you are a resident of the Philippines, we comply with the Data Privacy Act of 2012 and the regulations set by the National Privacy Commission. You have the right to access, correct, or erase your personal data and to object to its processing.</p>
        </div>
  
        <div id="changes" class="terms-section">
          <h2 class="section-title">11. Changes to Terms of Service</h2>
          <p>We may update these ToS from time to time. Any changes will be posted on this page with an updated "Effective Date." Continued use of the platform after changes constitutes your acceptance of the updated ToS.</p>
        </div>
  
        <div id="contact" class="terms-section">
          <h2 class="section-title">12. Contact Us</h2>
          <p>If you have any questions or concerns regarding these ToS or our privacy practices, please contact us at:</p>
          <p><a href="mailto:impactfulgames.supp@gmail.com">impactfulgames.supp@gmail.com</a></p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "Terms",
    data() {
      return {
        currentDate: new Date().toLocaleDateString("en-US", {
          year: "numeric",
          month: "long",
          day: "numeric",
        }),
      };
    },
  };
  </script>
  
  <style scoped>
  .terms-container {
    font-family: "Arial", sans-serif;
    max-width: 1000px;
    margin: 0 auto;
    padding: 2rem 1rem;
    color: #222;
    line-height: 1.5;
  }
  
  .terms-content {
    background-color: #fff;
  }
  
  .terms-title {
    font-size: 2.5rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
  }
  
  .effective-date {
    margin-bottom: 2rem;
    color: #333;
  }
  
  .terms-nav {
    display: flex;
    flex-direction: column;
    margin-bottom: 3rem;
  }
  
  .nav-link {
    color: #ff6000;
    text-decoration: none;
    margin-bottom: 0.75rem;
    font-weight: 500;
  }
  
  .nav-link:hover {
    text-decoration: underline;
  }
  
  .terms-section {
    margin-bottom: 3rem;
  }
  
  .section-title {
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 1.5rem;
  }
  
  .terms-list {
    list-style-type: disc;
    padding-left: 2rem;
    margin-bottom: 1.5rem;
  }
  
  .terms-list li {
    margin-bottom: 0.5rem;
  }
  
  p {
    margin-bottom: 1rem;
  }
  
  a {
    color: #ff6000;
    text-decoration: none;
  }
  
  a:hover {
    text-decoration: underline;
  }
  
  @media (max-width: 768px) {
    .terms-container {
      padding: 1.5rem 1rem;
    }
  
    .terms-title {
      font-size: 2rem;
    }
  
    .section-title {
      font-size: 1.75rem;
    }
  }
  </style>