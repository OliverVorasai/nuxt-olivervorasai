<template>
  <div>
    <!-- Navigation -->
    <nav class="flex justify-center">
      <a
        class="nav-btn"
        href="#websites-section"
        aria-label="Jump to websites section"
      >
        Websites
      </a>

      <a class="nav-btn" href="#work-section" aria-label="Jump to work section">
        Work
      </a>

      <a
        class="nav-btn"
        href="/Oliver Vorasai Resume.pdf"
        download
        target="_blank"
      >
        Download Resume
      </a>
    </nav>

    <Nuxt />

    <footer>
      <p>
        &copy;{{ new Date().getFullYear() }} — <strong>Oliver Vorasai</strong>
      </p>
    </footer>
  </div>
</template>

<style>
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>

<style lang="postcss" scoped>
.nav-btn {
  padding: 0.5rem;
  margin: 0.25rem;
  border-radius: 0.25rem;
}
.nav-btn:hover {
  color: #4299e1;
  background-color: #e2e8f0;
}

footer {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 4rem;
  border-top-width: 2px;
  font-size: 1.5rem;
  font-weight: 300;
}
</style>
