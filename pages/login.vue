<script lang="ts"></script>
<template>
 <client-only>
 <NavBar :navAdminMode="navAdminMode" />
 <div id="igMain" class="ig-main">
 <Login />
 </div>
 <Cookies />
 <Copyright />
 </client-only>
</template>
<script setup lang="ts">
import { useSeoMeta, useHead } from "@vueuse/head";
const title = "ImpactfulGames";
const description = "A game catalogue with interactive features that provide detailed information on video games across a wide range of genres, inspired by the structure and functionality of platforms like MyAnimeList.";

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
 { rel: "stylesheet", href: "https://fonts.googleapis.com/css2?family=DM+Serif+Text:ital@0;1&family=Russo+One&display=swap", },
 ],
});
const globalDelay = 500;
const allowCookies = useCookie<boolean>("allowCookies", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
allowCookies.value = allowCookies.value ?? false;
const retries = useCookie<number>("retries", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60,
});
retries.value = retries.value ?? 0;
const username = useCookie<string>("username", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
username.value = username.value ?? "";
const accessToken = useCookie<string>("accessToken", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
accessToken.value = accessToken.value ?? "";
const userLevel = useCookie<number>("userLevel", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
userLevel.value = userLevel.value ?? -1;

const fullName = useCookie<string>("fullName", {
 sameSite: "none",
 secure: true,
 maxAge: 60 * 60 * 24,
});
fullName.value = fullName.value ?? "";
const router = useRouter();
let navAdminMode = userLevel.value >= 2 ? "ig-nav-admin" : "";
const igServer = "https://impactfulgames-api.vercel.app";
type AuthResponse = {
 accessToken: string;
 userLevel: number;
 fullName: string;
 message: string;
};
function getByID<T extends HTMLElement>(id: string) {
 return document.getElementById(id) as T;
}
let lastLoginClicked = 0;
function checkAuthorizations() {
 if (accessToken.value) {
 if (userLevel.value <= 1) {
 router.push("/");
 } else if (userLevel.value >= 2) {
 router.push("/admin");
 }
 }
 const loginBox = getByID<HTMLDivElement>("igLoginBox");
 const loginForm = getByID<HTMLDivElement>("igLogInForm");
 const loginUsername = getByID<HTMLInputElement>("igLoginUsername");
 const loginPassword = getByID<HTMLInputElement>("igLoginPassword");
 const loginMessage = getByID<HTMLDivElement>("igLogInMessage");
 const logInActions = getByID<HTMLDivElement>("igLogInActions");
 const loginOK = getByID<HTMLDivElement>("igLoginOK");
 if (
 !loginBox ||
 !loginForm ||
 !loginUsername ||
 !loginPassword ||
 !loginMessage ||
 !logInActions ||
 !loginOK
 ) return;
 if (retries.value >= 3) {
 loginForm.classList.add("ig-hidden");
 loginMessage.classList.remove("ig-hidden");

 loginMessage.innerText = "Too many attempts, try again after 1 hour.";
 logInActions.classList.add("ig-hidden");
 return;
 }
 loginOK.dataset.busy = "0";
 loginBox.classList.remove("ig-hidden");
 loginOK.addEventListener("click", () => {
 if (loginOK.dataset.busy == "1") return;
 const tempUsername = loginUsername.value;
 const tempPassword = loginPassword.value;
 if (!tempUsername) {
 loginMessage.innerText = "Username is required.";
 loginMessage.classList.remove("ig-hidden");
 return;
 }
 if (!tempPassword) {
 loginMessage.innerText = "Password is required.";
 loginMessage.classList.remove("ig-hidden");
 return;
 }
 authorizeEmail(tempUsername, tempPassword);
 });
 loginUsername.addEventListener("keyup", (e) => {
 if (e.key === "Enter" && loginUsername.value) {
 loginPassword.focus();
 }
 });
 loginPassword.addEventListener("keyup", (e) => {
 if (e.key === "Enter") loginOK.click();
 });
 loadModal();
}
async function authorizeEmail(tempUsername: string, tempPassword: string) {
 if (lastLoginClicked >= Date.now() - globalDelay) return;
 lastLoginClicked = Date.now();
 const loginUsername = getByID<HTMLInputElement>("igLoginUsername");
 const loginPassword = getByID<HTMLInputElement>("igLoginPassword");
 const loginMessage = getByID<HTMLDivElement>("igLogInMessage");
 const loginOK = getByID<HTMLDivElement>("igLoginOK");
 if (!loginUsername || !loginPassword || !loginOK || !loginMessage) return;
 loginMessage.innerText = "";

 loginMessage.classList.add("ig-hidden");
 loginUsername.disabled = true;
 loginPassword.disabled = true;
 loginOK.dataset.busy = "1";
 try {
 userLevel.value = -1;
 const response = (await $fetch(`${igServer}/authorize`, {
 headers: { "Content-Type": "application/json" },
 method: "POST",
 body: {
 username: tempUsername,
 password: tempPassword,
 },
 })) as AuthResponse;
 accessToken.value = String(response.accessToken);
 userLevel.value = Number(response.userLevel);
 fullName.value = String(response.fullName);
 if (accessToken.value) {
 username.value = tempUsername;
 }
 loginOK.dataset.busy = "0";
 if (!accessToken.value) {
 retries.value = (retries.value || 0) + 1;
 }
 if (response.message) {
 loginMessage.innerText = response.message;
 loginMessage.classList.remove("ig-hidden");
 }
 } catch (e: any) {
 loginMessage.innerText = `Error encountered: ${e}`;
 loginMessage.classList.remove("ig-hidden");
 }
 loginUsername.disabled = false;
 loginPassword.disabled = false;
 loginUsername.value = "";
 loginPassword.value = "";
 loginOK.dataset.busy = "0";
 checkAuthorizations();
}
function loadModal() {
 const cookieModal = getByID<HTMLDivElement>("igCookieModal");
 const cookieBox = getByID<HTMLDivElement>("igCookieBox");
 const cookieX = getByID<HTMLDivElement>("igCookieX");
 const cookieOK = getByID<HTMLDivElement>("igCookieOK");
 if (!cookieModal || !cookieBox || !cookieX || !cookieOK) return;
 if (allowCookies.value === true) {
 allowAllCookies();

 return;
 }
 showCookiePopup();
 cookieX.addEventListener("click", () => {
 showCookiePopup(false);
 });
 cookieOK.addEventListener("click", () => {
 allowAllCookies();
 });
}
function showCookiePopup(show: boolean = true) {
 const cookieBox = getByID<HTMLDivElement>("igCookieBox");
 const cookieModal = getByID<HTMLDivElement>("igCookieModal");
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
function allowAllCookies() {
 if (lastCookieClicked >= Date.now() - globalDelay) return;
 lastCookieClicked = Date.now();
 allowCookies.value = true;
 showCookiePopup(false);
}
onMounted(() => {
 nextTick(checkAuthorizations);
});
</script>
<style>
.ig-login-box {
 position: absolute;
 top: 50%;
 left: 50%;
 transform: translate(-50%, -50%);
 width: 300px;
 padding: 20px;
 background: #fff;

 border-radius: 8px;
 border: 1px solid rgba(0, 0, 0, 0.1);
 box-shadow: 0 0 1px #000000bf;
}
.ig-login-header {
 font-size: 1.3em;
 font-weight: bold;
 text-align: center;
 line-height: 2em;
}
.ig-login-slogan {
 margin: 10px 0 20px 0;
 text-align: center;
}
.ig-login-form {
 margin-top: 20px;
}
.ig-login-input {
 margin-bottom: 10px;
 padding: 8px 10px;
 width: 100%;
 font-size: 1.1em;
 border-radius: 3px;
 border: 1px solid rgba(0, 0, 0, 0.3);
 outline: none;
}
.ig-login-message {
 padding: 8px;
 font-size: 0.7em;
 background-color: rgba(255, 0, 0, 0.1);
 border: 1px solid rgba(255, 0, 0, 0.3);
 border-radius: 3px;
}
.ig-login-actions {
 margin-top: 20px;
}
.ig-login-action {
 padding: 10px;
 text-align: center;
 border-radius: 6px;
 border: 1px solid rgba(0, 0, 0, 0.1);
 cursor: pointer;
}
.ig-login-ok {
 color: #fff;
 background-color: #3f7d58;

}
.ig-login-ok:hover {
 color: #fff;
 background-color: #3f7d58dd;
}
</style>