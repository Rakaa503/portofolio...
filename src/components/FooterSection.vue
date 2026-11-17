<script setup>
const year = new Date().getFullYear()
</script>

<template>
  <footer class="footer section-wrap">
    <a class="brand" href="#home">AVILLA<span>.DEV</span></a>
    <p class="footer-tagline">BUILD NOW. SECURE FIRST. <span>— RAKHA AVILLA</span></p>
    <nav class="footer-links" aria-label="Footer links">
      <a href="https://github.com/Rakaa503" target="_blank" rel="noopener noreferrer">GitHub</a>
      <a href="https://www.instagram.com/rakhaaviillarn/" target="_blank" rel="noopener noreferrer">Instagram</a>
      <a href="mailto:AviDevelopmentStudio@gmail.com">Email</a>
      <a href="https://wa.me/6283872394590" target="_blank" rel="noopener noreferrer">WhatsApp</a>
    </nav>
    <span class="footer-copyright">© {{ year }} Rakha Avilla. All rights reserved.</span>
  </footer>
</template>
