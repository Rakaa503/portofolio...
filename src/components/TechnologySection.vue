<script setup>
const groups = [
  { title: 'Programming Languages', items: ['JavaScript', 'TypeScript', 'Go', 'Python', 'PHP'] },
  { title: 'Frontend', items: ['Vue.js', 'PrimeVue', 'AURA', 'Nuxt', 'Chakra'] },
  { title: 'Backend', items: ['Elysia.js','node js', 'Hono', 'Bun', 'Fastify'] },
  { title: 'Database & ORM', items: ['PostgreSQL', 'MySQL', 'Prisma', 'GORM'] },
  { title: 'AI & Machine Learning', items: ['Python', 'Machine Learning','Scikit Learn', 'NLP', 'Information Retrieval'] },
  { title: 'Security', items: ['JWT', 'Authentication', 'Authorization', 'OWASP Concepts', 'NIST SSDF Concepts', 'Application Security Testing'] },
  { title: 'Development Tools', items: ['Git', 'GitHub', 'VS Code', 'Linux', 'Postman'] },
]
</script>

<template>
  <section id="technologies" class="section-pad technologies-section reveal" aria-labelledby="technologies-title">
    <div class="section-wrap">
      <p class="section-label"><span>04</span> / TECHNOLOGIES</p>
      <div class="expertise-heading">
        <h2 id="technologies-title">Tools for the<br /><span>work in progress.</span></h2>
        <p>A snapshot of technologies and areas I’m learning and exploring—not a list of certifications.</p>
      </div>
      <div class="technology-groups">
        <div v-for="group in groups" :key="group.title" class="technology-group">
          <h3>{{ group.title }}</h3>
          <div class="tech-list"><span v-for="item in group.items" :key="item">{{ item }}</span></div>
        </div>
      </div>
    </div>
  </section>
</template>
