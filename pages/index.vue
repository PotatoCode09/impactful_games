<script lang="ts"></script>
<template>
  <client-only>
    <NavBar :navAdminMode="navAdminMode" />
    <div id="igMain" class="ig-main">
      <span id="igPageTitle" class="ig-page-title ig-hidden">Latest</span>
      <div id="igContainer" class="ig-container"></div>
    </div>
    <Cookies />
    <AboutUs />
    <Copyright />
  </client-only>
</template>
<script setup lang="ts">
import { useSeoMeta, useHead } from "@vueuse/head";
const title = "ImpactfulGames";
const description =
  "A game catalogue with interactive features that provide detailed information on video games across a wide range of genres, inspired by the structure and functionality of platforms like MyAnimeList.";

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

type ContentItem = {
  id: string;
  author: string;
  title: string;
  content: string;
  isSynchronized: number;
  createdAt: number;
};
type ContentResponse = {
  contents: ContentItem[];
};
const router = useRouter();
const igServer = "https://impactfulgames-api.vercel.app";
let navAdminMode = userLevel.value >= 2 ? "ig-nav-admin" : "";
function getByID<T extends HTMLElement>(id: string) {
  return document.getElementById(id) as T;
}
function checkAuthorizations() {
  if (!accessToken.value) {
    router.push("/login");
  } else if (userLevel.value >= 2) {
    router.push("/admin");
  }
  const navBasic = getByID<HTMLDivElement>("igNavBasic");
  const navAdmin = getByID<HTMLDivElement>("igNavAdmin");
  const navLogout = getByID<HTMLDivElement>("igNavBasicLogout");
  const pageTitle = getByID<HTMLSpanElement>("igPageTitle");
  if (!navBasic || !navAdmin || !navLogout || !pageTitle) return;
  navLogout.addEventListener("click", (e) => {
    retries.value = 0;
    username.value = "";
    accessToken.value = "";
    userLevel.value = -1;
    fullName.value = "";
    router.push("/login");
  });
  navAdmin.remove();
  navBasic.classList.remove("ig-hidden");
  pageTitle.classList.remove("ig-hidden");
  loadModal();
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
  loadContents();
}
onMounted(() => {
  nextTick(() => {
    checkAuthorizations();
  });
});
async function loadContents() {
  if (!accessToken.value) return;
  var rawContents = [] as ContentItem[];
  try {
    const query = new URLSearchParams({
      username: username.value,
      userLevel: String(userLevel.value),
      accessToken: accessToken.value,
    }).toString();
    const response = (await $fetch(`${igServer}/get_contents?${query}`, {
      headers: { "Content-Type": "application/json" },
      method: "GET",
    })) as ContentResponse;
    rawContents = response.contents;
  } catch (e: any) {
    return;
  }
  const container = getByID<HTMLDivElement>("igContainer");
  if (!container) return;
  container.innerHTML = "";
  const contents = renderContents(rawContents) as HTMLElement;
  container.appendChild(contents);
}
function renderContents(data: ContentItem[]): HTMLElement {
  const parent = document.createElement("div");
  parent.className = "ig-contents";
  data.forEach((item, index) => {
    const wrapper = document.createElement("div");
    wrapper.id = `content-${index}`;
    wrapper.className = "ig-content-box";
    const title = document.createElement("h2");
    title.className = "ig-content-title";
    title.textContent = item.title;
    const meta = document.createElement("p");
    const date = new Date(item.createdAt * 1000);
    const published = date.toLocaleDateString("en-US", {
      year: "numeric",
      month: "long",
      day: "numeric",
    });
    meta.textContent = `by ${item.author} • ${published}`;
    meta.className = "ig-content-meta";
    const content = document.createElement("p");
    content.className = "ig-content-data";
    content.textContent = item.content;
    wrapper.append(title, meta, content);
    parent.appendChild(wrapper);
  });
  return parent;
}
</script>
<style>
.ig-nav-link:hover {
  cursor: pointer;
}
.ig-page-title {
  position: relative;
  margin: 60px auto 0;
  width: 800px;
  max-width: 90%;
  padding: 20px;
  font-size: 1.8em;
  font-weight: bold;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  display: block;
}
.ig-container {
  position: relative;
  margin: 20px auto 0;
  width: 800px;
  max-width: 90%;
}
.ig-content-box {
  margin-bottom: 10px;
  padding: 20px;
  background: #fff;
  border-radius: 3px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  cursor: pointer;
}
.ig-content-title {
  line-height: 1.5em;
  font-weight: bold;
}
.ig-content-meta {
  font-size: 0.8em;
  color: #666;
}
.ig-content-data {
  margin-top: 10px;
  line-height: 1.5em;
}
</style>
