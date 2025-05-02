<template>
    <client-only>
    <header :class="['ig-navbar', navAdminMode]">
    <nav class="ig-nav-left">
    <a href="/" class="ig-nav-home">
    <img src="/joystick.png" width=20 height=20 class="ig-nav-logo">
    <span>ImpactfulGames</span>
    </a>
    </nav>
    <nav id="igNavBasic" class="ig-nav-right ig-hidden">
    <ul>
    <li><a href="#" class="ig-nav-link">Trending</a></li>
    <li><a href="#" class="ig-nav-link">Most Viewed</a></li>
    <li><a href="#" class="ig-nav-link">Hot</a></li>
    <li><span id="igNavBasicLogout" class="ig-nav-link">Logout</span></li>
    </ul>
    </nav>
    <nav id="igNavAdmin" class="ig-nav-right ig-hidden">
    <ul>
    <li><a href="#" class="ig-nav-link">Settings</a></li>
    <li><a href="#" class="ig-nav-link">Reports</a></li>
    <li><span id="igNavAdminLogout" class="ig-nav-link">Logout</span></li>
    </ul>
    </nav>
    </header>
    </client-only>
   </template>
   <script setup lang="ts">
   const props = defineProps<{ navAdminMode: string }>();
   </script>