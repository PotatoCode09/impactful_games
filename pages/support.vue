<template>
  <client-only>
    <NavBar />
    <main id="igMain" class="ig-main">
      <section class="ig-support">
        <h1>Account Deletion</h1>
        <p><strong>Effective Date:</strong> {{ effectiveDate }}</p>

        <h2>Data Retention and Deletion</h2>
        <p>
          You can request the deletion of your account and all associated data
          at any time. When you delete your account, all your personal data and
          inputted information will be permanently removed from our systems.
        </p>

        <p>
          Please contact us at
          <a href="mailto:impactfulgames.supp@gmail.com"
            >impactfulgames.supp@gmail.com</a
          >.
        </p>
      </section>
    </main>
    <AboutUs />
    <Copyright />
  </client-only>
</template>


<script setup lang="ts">
import { useSeoMeta, useHead } from "@vueuse/head";
import NavBar from "@/components/NavBar.vue";
import Copyright from "@/components/Copyright.vue";

// Dynamic effective date
const effectiveDate = new Date().toLocaleDateString(undefined, {
  year: "numeric",
  month: "long",
  day: "numeric",
});

const title = "Impactful Games | Support";
const description =
  "Learn about our account deletion policy and how we handle data retention and deletion requests.";

useSeoMeta({
  title: () => title,
  description: () => description,
  charset: "utf-8",
  viewport: "width=device-width, initial-scale=1.0",
});

useHead({
  link: [
    { rel: "icon", type: "image/png", href: "/joystick.png" },
    { rel: "stylesheet", href: "/reset.css" },
    { rel: "stylesheet", href: "/custom.css" },
    { rel: "preconnect", href: "https://fonts.googleapis.com" },
    { rel: "preconnect", href: "https://fonts.gstatic.com", crossorigin: "" },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=DM+Serif+Text:ital@0;1&family=Russo+One&display=swap",
    },
  ],
});
</script>


<style scoped>
/* Add any scoped styles here if necessary */
</style>
