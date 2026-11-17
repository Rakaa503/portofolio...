<script setup>
const projects = [
  {
    number: '01',
    title: 'AVSS Lite',
    category: 'APPLICATION SECURITY · TYPESCRIPT',
    description: 'A lightweight TypeScript security and authentication framework designed to provide reusable security capabilities for modern applications.',
    features: ['JWT Authentication', 'Session Management', 'OAuth Providers', 'Route Guards & Permissions', 'Authentication Hooks', 'Cache, logging & security utilities'],
    focus: 'Authentication architecture, reusable modules, application security testing, and developer experience.',
    flow: '',
    stack: ['TypeScript', 'Node.js ecosystem', 'Prisma', 'Authentication tooling', 'Testing tools'],
    url: 'https://github.com/Rakaa503/AviDev-Security-System',
    cta: 'VIEW SOURCE CODE',
  },
  {
    number: '02',
    title: 'AviGo',
    category: 'ARTIFICIAL INTELLIGENCE · NLP · INFORMATION RETRIEVAL',
    description: 'An exploration of human–AI interaction through contextual understanding, memory, decision-making, and knowledge retrieval.',
    features: ['Interaction analysis & intent understanding', 'Context and conversation memory', 'Decision engine & action routing', 'Knowledge retrieval & semantic search', 'Hybrid ranking', 'Recommendation & explanation'],
    focus: 'An architectural and AI system exploration; not currently under active development or presented as a production service.',
    flow: 'Human input → interaction analysis → intent & topic understanding → context & memory → decision engine → action routing → knowledge retrieval → hybrid ranking → response generation.',
    stack: ['Go', 'Python', 'Machine Learning', 'NLP', 'Information Retrieval'],
    url: 'https://github.com/Rakaa503/interaction-human-with-ai',
    cta: 'EXPLORE REPOSITORY',
  },
  {
    number: '03',
    title: 'AviCore',
    category: 'BACKEND ENGINEERING · REST API',
    description: 'A backend REST API project focused on structured application architecture, authentication, authorization, data validation, and API security.',
    features: ['JWT & role-based access control', 'User, product & order management', 'Zod validation & rate limiting', 'Security headers & CORS protection', 'Centralized error handling', 'PostgreSQL integration'],
    focus: 'A practical order workflow from login and product browsing through confirmation, payment, and completion.',
    flow: 'Login → view products → create order → pending → WhatsApp confirmation → waiting payment → paid → processing → completed.',
    stack: ['Bun', 'Hono', 'TypeScript', 'Prisma', 'PostgreSQL', 'Zod', 'AVSS Lite'],
    url: 'https://github.com/Rakaa503/Avicore',
    cta: 'VIEW SOURCE CODE',
  },
]
</script>

<template>
  <section id="projects" class="section-pad section-wrap reveal" aria-labelledby="projects-title">
    <p class="section-label"><span>05</span> / SELECTED PROJECTS</p>
    <div class="projects-heading">
      <h2 id="projects-title">Building systems<br /><span>with purpose.</span></h2>
      <p>Personal projects and explorations shaped by a practical, security-conscious mindset.</p>
    </div>
    <article v-for="project in projects" :key="project.number" class="project-row">
      <p class="project-number">{{ project.number }}</p>
      <div class="project-main">
        <p class="project-category">{{ project.category }}</p>
        <h3>{{ project.title }}</h3>
        <p class="project-description">{{ project.description }}</p>
        <ul class="project-details"><li v-for="feature in project.features" :key="feature">{{ feature }}</li></ul>
        <p class="project-note"><strong>Engineering focus</strong> — {{ project.focus }}</p>
        <p v-if="project.flow" class="project-flow"><strong>System flow</strong><span>{{ project.flow }}</span></p>
        <div class="project-stack" aria-label="Technology stack"><span v-for="item in project.stack" :key="item">{{ item }}</span></div>
      </div>
      <a class="project-link" :href="project.url" target="_blank" rel="noopener noreferrer" :aria-label="`${project.cta}: ${project.title} on GitHub`">
        {{ project.cta }} <span aria-hidden="true">↗</span>
      </a>
    </article>
  </section>
</template>
