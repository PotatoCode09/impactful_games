<script setup lang="ts">
 const year = new Date().getFullYear();
</script>
<template>
    <client-only>
 <footer class="ig-footer-area">
 <nav class="ig-footer-links">
 <a href="/terms">Terms of Service</a>
 <span>&nbsp;|&nbsp;</span>
 <a href="/policy">Privacy Policy</a>
 <span>&nbsp;|&nbsp;</span>
 <a href="support">Support</a>
 </nav>
 <div class="ig-footer-copyright">
 <span>&copy;&nbsp;</span>
 <span>{{ year }}</span>
 <span>&nbsp;Kamotech. All rights reserved.</span>
 </div>
 </footer>
 </client-only>
</template>
