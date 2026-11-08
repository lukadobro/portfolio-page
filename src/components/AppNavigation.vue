<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const isOpen = ref(false)
const menuButton = ref(null)

function closeMenu() {
  isOpen.value = false
}

function handleEscape(event) {
  if (event.key === 'Escape' && isOpen.value) {
    closeMenu()
    menuButton.value?.focus()
  }
}

onMounted(() => window.addEventListener('keydown', handleEscape))
onUnmounted(() => window.removeEventListener('keydown', handleEscape))
</script>

<template>
  <header class="site-header">
    <nav class="navigation" aria-label="Hauptnavigation">
      <a class="navigation__logo" href="#start" aria-label="LD. – Zum Startbereich" @click="closeMenu">
        LD.
      </a>

      <button
        ref="menuButton"
        class="navigation__toggle"
        type="button"
        :aria-expanded="isOpen"
        aria-controls="navigation-links"
        :aria-label="isOpen ? 'Menü schliessen' : 'Menü öffnen'"
        @click="isOpen = !isOpen"
      >
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
          <path v-if="isOpen" d="m6 6 12 12M6 18 18 6" />
          <path v-else d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>

      <ul id="navigation-links" class="navigation__links" :class="{ 'navigation__links--open': isOpen }">
        <li><a href="#start" @click="closeMenu">Home</a></li>
        <li>
          <a href="https://github.com/lukadobro" target="_blank" rel="noopener noreferrer" @click="closeMenu">
            <svg class="navigation__icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true" focusable="false">
              <path d="M12 .75a11.25 11.25 0 0 0-3.56 21.92c.56.1.77-.24.77-.54v-2.1c-3.13.68-3.79-1.33-3.79-1.33-.51-1.3-1.25-1.65-1.25-1.65-1.02-.7.08-.69.08-.69 1.13.08 1.72 1.16 1.72 1.16 1 1.72 2.63 1.22 3.27.93.1-.73.39-1.22.71-1.5-2.5-.28-5.12-1.25-5.12-5.56 0-1.23.44-2.23 1.16-3.02-.12-.28-.5-1.43.11-2.98 0 0 .95-.3 3.1 1.15a10.8 10.8 0 0 1 5.63 0c2.15-1.46 3.09-1.15 3.09-1.15.62 1.55.23 2.7.11 2.98.73.79 1.16 1.79 1.16 3.02 0 4.32-2.62 5.27-5.13 5.55.4.35.76 1.03.76 2.08v3.11c0 .3.2.65.77.54A11.25 11.25 0 0 0 12 .75Z" />
            </svg>
            <span class="visually-hidden">GitHub (öffnet in neuem Tab)</span>
          </a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/luka-dobrosavljevic-9444713b3/" target="_blank" rel="noopener noreferrer" @click="closeMenu">
            <svg class="navigation__icon" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true" focusable="false">
              <path d="M20.45 2H3.55C2.69 2 2 2.68 2 3.52v16.96c0 .84.69 1.52 1.55 1.52h16.9c.86 0 1.55-.68 1.55-1.52V3.52c0-.84-.69-1.52-1.55-1.52ZM7.93 18.75H4.98V9.2h2.95v9.55ZM6.45 7.9a1.71 1.71 0 1 1 0-3.42 1.71 1.71 0 0 1 0 3.42Zm12.3 10.85H15.8v-4.64c0-1.11-.02-2.54-1.55-2.54-1.55 0-1.79 1.21-1.79 2.46v4.72H9.51V9.2h2.83v1.3h.04c.39-.74 1.36-1.53 2.79-1.53 2.99 0 3.58 1.97 3.58 4.53v5.25Z" />
            </svg>
            <span class="visually-hidden">LinkedIn (öffnet in neuem Tab)</span>
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>
.site-header {
  position: sticky;
  top: 0;
  z-index: 10;
  background: #101719;
  padding-inline: clamp(1.5rem, 6vw, 6rem);
  border-bottom: 1px solid #293638;
}

.navigation {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 1rem;
  max-width: 72rem;
  margin-inline: auto;
  padding-block: 1rem;
}

.navigation a {
  display: inline-flex;
  align-items: center;
  min-height: 2.75rem;
  min-width: 2.75rem;
  padding: 0.5rem;
  color: #b6c3c7;
  line-height: 1.5;
  text-decoration: none;
}

.navigation .navigation__logo {
  color: #78d5c5;
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: -0.04em;
}

.navigation a:hover {
  color: #78d5c5;
}

.navigation__icon {
  display: block;
  flex-shrink: 0;
  width: 1.5rem;
  height: 1.5rem;
}

.navigation a:focus-visible,
.navigation__toggle:focus-visible {
  outline: 2px solid #78d5c5;
  outline-offset: 4px;
  border-radius: 0.25rem;
}

.navigation__links {
  display: flex;
  gap: clamp(1rem, 3vw, 2rem);
  margin: 0;
  padding: 0;
  list-style: none;
}

.navigation__toggle {
  display: none;
  align-items: center;
  justify-content: center;
  width: 2.75rem;
  height: 2.75rem;
  padding: 0;
  border: 1px solid #526467;
  border-radius: 0.25rem;
  background: transparent;
  color: #eef3f4;
  cursor: pointer;
}

.navigation__toggle:hover {
  color: #78d5c5;
  border-color: currentColor;
}

.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip-path: inset(50%);
  white-space: nowrap;
  border: 0;
}

@media (width < 48rem) {
  .navigation__toggle {
    display: inline-flex;
  }

  .navigation__links {
    display: none;
    flex-basis: 100%;
    flex-direction: column;
    gap: 0.25rem;
    padding-top: 0.75rem;
    border-top: 1px solid #293638;
  }

  .navigation__links--open {
    display: flex;
  }

  .navigation__links a {
    width: 100%;
  }
}
</style>
