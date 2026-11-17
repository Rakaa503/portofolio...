<script setup>
import { onMounted, onUnmounted } from 'vue'
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import EducationSection from './components/EducationSection.vue'
import ExpertiseSection from './components/ExpertiseSection.vue'
import TechnologySection from './components/TechnologySection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import PhilosophySection from './components/PhilosophySection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

let revealObserver

onMounted(() => {
  const revealItems = document.querySelectorAll('.reveal')
  if (!('IntersectionObserver' in window)) {
    revealItems.forEach((item) => item.classList.add('is-visible'))
    return
  }

  revealObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible')
        observer.unobserve(entry.target)
      }
    })
  }, { threshold: 0.12 })

  revealItems.forEach((item) => revealObserver.observe(item))
})

onUnmounted(() => revealObserver?.disconnect())
</script>

<template>
  <div class="site-shell">
    <a class="skip-link" href="#main-content">Skip to content</a>
    <Navbar />
    <main id="main-content">
      <HeroSection />
      <AboutSection />
      <EducationSection />
      <ExpertiseSection />
      <TechnologySection />
      <ProjectsSection />
      <PhilosophySection />
      <ContactSection />
    </main>
    <FooterSection />
  </div>
</template>
