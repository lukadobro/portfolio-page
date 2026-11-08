<template>
  <section id="about" class="about" aria-labelledby="about-title">
    <div class="about__container">
      <h2 id="about-title">Über mich</h2>
      <div class="about__text">
        <p class="about__intro">Softwareentwicklung mit Fokus auf moderne Webanwendungen.</p>
        <p>
          Ich bin Full-Stack Developer mit beruflicher Erfahrung in der Entwicklung und
          Weiterentwicklung von Webanwendungen. Mein technischer Schwerpunkt liegt auf
          C#, .NET, Vue.js und relationalen Datenbanken.
        </p>
        <p>
          Ich habe sowohl an neuen Anwendungen als auch an der Modernisierung bestehender
          Systeme mitgearbeitet. Dabei interessieren mich besonders nachvollziehbare
          Architekturen, wartbarer Code und praxisorientierte Lösungen.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  scroll-margin-top: 6rem;
  padding: clamp(3rem, 8vw, 7rem) clamp(1.5rem, 6vw, 6rem);
  border-top: 1px solid #293638;
}

.about__container {
  display: grid;
  gap: clamp(2rem, 5vw, 4rem);
  max-width: 72rem;
  margin-inline: auto;
}

h2 {
  margin: 0;
  color: #78d5c5;
  font-size: clamp(1.75rem, 3vw, 2.5rem);
  font-weight: 650;
  line-height: 1.2;
  letter-spacing: -0.03em;
}

.about__text {
  min-width: 0;
  max-width: 65ch;
  color: #b6c3c7;
  font-size: clamp(1rem, 1.3vw, 1.125rem);
  line-height: 1.8;
  overflow-wrap: break-word;
}

p {
  margin: 0;
}

p + p {
  margin-top: 1.5rem;
}

.about__intro {
  color: #eef3f4;
  font-size: clamp(1.25rem, 2vw, 1.5rem);
  line-height: 1.5;
}

@media (width >= 64rem) {
  .about__container {
    grid-template-columns: 1fr 2fr;
    align-items: start;
  }
}
</style>
