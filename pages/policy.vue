<script setup lang="ts">
const title = ref("impactful_games | Home");
const description = ref("Game catalouge detailing various games with interactive features.");
useSeoMeta({
 title: () => title.value,
 description: () => `${title.value} - ${description.value}`,
 charset: "utf-8",
 viewport: "width=device-width, initial-scale=1.0",
 robots: "index, follow",
 ogTitle: () => title.value,
 ogDescription: () => `${title.value} - ${description.value}`,
 // ogImage: "https://impactful_games.vercel.app/featured.jpg",
 // twitterCard: "summary_large_image",
});
</script>

<template>
    <Html lang="en">
    <Head>
    <Link rel="icon" type="image/png" href="logo.png" />
    <link rel="stylesheet" href="/reset.css" />
    </Head>
    </Html>
   
    <client-only>
    <Welcome />
    </client-only>
   </template>
   <style scoped></style>