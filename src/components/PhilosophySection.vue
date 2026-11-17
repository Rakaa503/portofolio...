<script setup>
const principles = [
  { number: '01', title: 'Build with Purpose', description: 'Every feature should solve a meaningful problem.' },
  { number: '02', title: 'Security by Design', description: 'Security belongs from the beginning, not as an afterthought.' },
  { number: '03', title: 'Simplicity over Complexity', description: 'Prefer clear architecture and maintainable implementations.' },
  { number: '04', title: 'Continuous Learning', description: 'Improve through experimentation, testing, research, and iteration.' },
  { number: '05', title: 'Engineering with Responsibility', description: 'Build systems that are reliable, understandable, and respectful of users.' },
]
</script>

<template>
  <section id="philosophy" class="section-pad section-wrap principles-section reveal" aria-labelledby="philosophy-title">
    <p class="section-label"><span>06</span> / PHILOSOPHY</p>
    <div class="principles-content">
      <h2 id="philosophy-title">Engineering is more than <span>writing code.</span></h2>
      <div class="principle-list">
        <article v-for="principle in principles" :key="principle.number">
          <span>{{ principle.number }}</span><strong>{{ principle.title }}</strong><p>{{ principle.description }}</p>
        </article>
      </div>
    </div>
  </section>
</template>
