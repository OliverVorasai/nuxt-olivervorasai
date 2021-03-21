<template>
  <div>
    <!-- Navigation -->
    <nav class="flex justify-center">
      <a
        class="nav-btn"
        href="#websites-section"
        aria-label="Jump to websites section"
        >Websites</a
      >
      <a class="nav-btn" href="#work-section" aria-label="Jump to work section"
        >Work</a
      >
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
    <footer class="flex justify-center border-t-2 h-16">
      <div class="self-center text-2xl font-light">
        <p>
          &copy;{{ new Date().getFullYear() }} — <strong>Oliver Vorasai</strong>
        </p>
      </div>
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

<style scoped lang="postcss">
/* Styles for nav buttons */
.nav-btn {
  @apply py-2 px-2 m-1 rounded;
}
.nav-btn:hover {
  @apply text-blue-500 bg-gray-300;
}
</style>
