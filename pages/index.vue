<script lang="ts"></script>
<template>
 <client-only>
  <NavBar />
 <div id="igMain" class="ig-main"></div>
  <Cookies /> 
  <Copyright /> 
 </client-only>
</template>
<script setup lang="ts">

import { useSeoMeta, useHead } from '@vueuse/head';
const title = "Impactful Games | Home";
const description = "A game catalogue with interactive features that provide detailed information on video games across a wide range of genres, inspired by the structure and functionality of platforms like MyAnimeList.";
useSeoMeta({
 title: () => title,
 description: () => description,
 charset: "utf-8",
 viewport: "width=device-width, initial-scale=1.0"
});
useHead({
  link: [
    { rel: 'icon', type: 'image/png', href: '/joystick.png' },
    { rel: 'stylesheet', href: '/reset.css' },
    { rel: 'stylesheet', href: '/custom.css' },
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com', crossorigin: '' },
    { rel: 'stylesheet', href: 'https://fonts.googleapis.com/css2?family=DM+Serif+Text:ital@0;1&family=Russo+One&display=swap' }
  ]
});
const globalDelay = 500;
const allowCookies = useCookie<boolean>("allowCookies", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
allowCookies.value = allowCookies.value || false;
async function loadModal() {
 const cookieModal = document.getElementById("igCookieModal") as HTMLDivElement;
 const cookieBox = document.getElementById("igCookieBox") as HTMLDivElement;
 const cookieX = document.getElementById("igCookieX") as HTMLDivElement;
 const cookieOK = document.getElementById("igCookieOK") as HTMLDivElement;
 if ( !cookieModal || !cookieBox || !cookieX || !cookieOK ) return;
 if (allowCookies.value === true) {
 allowAllCookies();
 return;
 }
 showCookiePopup();
 cookieX.addEventListener("click", (e) => {
 showCookiePopup(false);
 });
 cookieOK.addEventListener("click", (e) => {
 allowAllCookies();
 });
}
async function showCookiePopup(show: boolean = true) {
 const cookieBox = document.getElementById("igCookieBox") as HTMLDivElement;
 const cookieModal = document.getElementById("igCookieModal") as HTMLDivElement;
 if (!cookieBox || !cookieModal) {
 setTimeout(showCookiePopup, 50);
 return;
 }
 if (!show) {
 cookieBox.classList.add("ig-hidden");
 cookieModal.classList.add("ig-hidden");
 return;
 }

 cookieBox.classList.remove("ig-hidden");
 cookieModal.classList.remove("ig-hidden");
}
let lastCookieClicked = 0;
async function allowAllCookies() {
 if (lastCookieClicked >= Date.now() - globalDelay) return;
 lastCookieClicked = Date.now();
 allowCookies.value = true;
 showCookiePopup(false);
}
onMounted(() => {
 setTimeout(() => {
 loadModal();
 }, 1);
});

</script>


<style scoped></style>
<style></style>