<script setup>
import AppNavigation from './components/AppNavigation.vue'
import AboutSection from './components/AboutSection.vue'
</script>

<template>
  <AppNavigation />
  <main>
    <section id="start" class="hero" aria-labelledby="hero-title">
      <div class="hero__content">
        <p class="hero__eyebrow">Persönliches Entwickler-Portfolio</p>
        <h1 id="hero-title">Luka <span>Dobrosavljevic</span></h1>
        <p class="hero__role">Full-Stack Developer</p>
      </div>
    </section>
    <AboutSection />
  </main>
</template>
