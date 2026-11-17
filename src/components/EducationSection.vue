<script setup>
const education = [
  {
    number: '01',
    institution: 'Sekolah Tinggi Teknologi Mandala',
    focus: 'Informatics Engineering',
    period: '2024 — PRESENT',
    description: 'Currently pursuing Informatics Engineering, developing knowledge in software development, computing, information systems, and technology.',
  },
  {
    number: '02',
    institution: 'SMAN 2 Padalarang',
    focus: 'Senior High School',
    period: '2021 — 2024',
    description: 'Completed senior high school education before continuing into Informatics Engineering.',
  },
]
</script>

<template>
  <section id="education" class="section-pad section-wrap reveal" aria-labelledby="education-title">
    <div class="section-intro">
      <p class="section-label"><span>02</span> / EDUCATION</p>
      <h2 id="education-title">Learning is part of<br /><span>the engineering process.</span></h2>
    </div>
    <div class="education-timeline">
      <article v-for="item in education" :key="item.number" class="education-item">
        <span class="education-marker" aria-hidden="true"></span>
        <p class="education-period">{{ item.period }}</p>
        <div class="education-details">
          <p class="card-number">{{ item.number }} / EDUCATION</p>
          <h3>{{ item.institution }}</h3>
          <p class="education-focus">{{ item.focus }}</p>
          <p class="education-description">{{ item.description }}</p>
        </div>
      </article>
    </div>
  </section>
</template>
