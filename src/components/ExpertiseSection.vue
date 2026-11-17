<script setup>
const areas = [
  { number: '01', title: 'Fullstack Development', description: 'Building web applications and backend systems with structured architecture and maintainable code.', focus: ['Frontend Engineering', 'Backend Development', 'REST API Development', 'Database Design', 'Application Integration'] },
  { number: '02', title: 'AI & Machine Learning', description: 'Exploring intelligent systems that understand information, process context, and retrieve relevant knowledge.', focus: ['Machine Learning', 'Natural Language Processing', 'Semantic Search', 'Information Retrieval', 'Intelligent Systems'] },
  { number: '03', title: 'Cybersecurity', description: 'Applying security principles to software systems and understanding how applications can be protected against common threats.', focus: ['Application Security', 'Authentication', 'Authorization', 'Input Validation', 'Security Testing', 'Secure Development'] },
  { number: '04', title: 'Software Engineering', description: 'Designing reliable and maintainable systems through structured engineering practices.', focus: ['Software Architecture', 'Clean Code', 'System Design', 'Testing', 'Documentation', 'Maintainability'] },
]
</script>

<template>
  <section id="expertise" class="section-pad section-wrap reveal" aria-labelledby="expertise-title">
    <p class="section-label"><span>03</span> / EXPERTISE</p>
    <div class="expertise-heading">
      <h2 id="expertise-title">Four disciplines.<br /><span>One engineering mindset.</span></h2>
      <p>A broad foundation, guided by curiosity and a commitment to building with care.</p>
    </div>
    <div class="expertise-grid">
      <article v-for="area in areas" :key="area.number" class="expertise-card">
        <p class="card-number">{{ area.number }} <span>— AREA OF FOCUS</span></p>
        <h3>{{ area.title }}</h3>
        <p class="expertise-description">{{ area.description }}</p>
        <ul class="focus-list"><li v-for="focus in area.focus" :key="focus">{{ focus }}</li></ul>
      </article>
    </div>
  </section>
</template>
