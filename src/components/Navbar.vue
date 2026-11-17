<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const links = [
  { label: 'Home', id: 'home' },
  { label: 'About', id: 'about' },
  { label: 'Expertise', id: 'expertise' },
  { label: 'Projects', id: 'projects' },
  { label: 'Contact', id: 'contact' },
]

const activeSection = ref('home')
const menuOpen = ref(false)
const scrolled = ref(false)
let sectionObserver

function closeMenu() {
  menuOpen.value = false
}

function onKeydown(event) {
  if (event.key === 'Escape') closeMenu()
}

function onScroll() {
  scrolled.value = window.scrollY > 12
}

onMounted(() => {
  if ('IntersectionObserver' in window) {
    sectionObserver = new IntersectionObserver((entries) => {
      const visible = entries
        .filter((entry) => entry.isIntersecting)
        .sort((a, b) => b.intersectionRatio - a.intersectionRatio)[0]
      if (visible) activeSection.value = visible.target.id
    }, { rootMargin: '-20% 0px -60% 0px', threshold: [0, 0.15, 0.4] })

    links.forEach(({ id }) => {
      const section = document.getElementById(id)
      if (section) sectionObserver.observe(section)
    })
  }
  onScroll()
  window.addEventListener('scroll', onScroll, { passive: true })
  window.addEventListener('keydown', onKeydown)
})

onUnmounted(() => {
  sectionObserver?.disconnect()
  window.removeEventListener('scroll', onScroll)
  window.removeEventListener('keydown', onKeydown)
})
</script>

<template>
  <header class="topbar" :class="{ 'topbar-scrolled': scrolled }">
    <a class="brand" href="#home" aria-label="AVILLA.DEV home" @click="closeMenu">
      AVILLA<span>.DEV</span>
    </a>
    <button
      class="menu-toggle"
      type="button"
      :aria-expanded="menuOpen"
      aria-controls="primary-navigation"
      :aria-label="menuOpen ? 'Close navigation menu' : 'Open navigation menu'"
      @click="menuOpen = !menuOpen"
    >
      <span></span><span></span>
    </button>
    <nav id="primary-navigation" class="nav-links" :class="{ 'nav-open': menuOpen }" aria-label="Main navigation">
      <a
        v-for="link in links"
        :key="link.id"
        :href="`#${link.id}`"
        :class="{ 'nav-active': activeSection === link.id }"
        :aria-current="activeSection === link.id ? 'location' : undefined"
        @click="closeMenu"
      >{{ link.label }}</a>
      <a class="nav-contact" href="#contact" @click="closeMenu">Let’s talk <span aria-hidden="true">↗</span></a>
    </nav>
  </header>
</template>
