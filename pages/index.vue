<template>
  <div class="container">
    <!-- Navigation -->
    <nav class="flex justify-center">
      <a class="nav-btn" href="#project-section">Projects</a>
      <a class="nav-btn" href="#work-section">Work</a>
      <a
        class="nav-btn"
        href="/Oliver Vorasai Resume.pdf"
        download
        target="_blank"
      >
        Download Resume
      </a>
    </nav>

    <!-- Feature -->
    <section class="flex flex-col text-center my-12">
      <h1 class="text-6xl">Oliver Vorasai</h1>
      <h2 class="text-4xl text-gray-700">Front End Developer</h2>
      <div class="flex flex-row justify-center">
        <a
          class="outline-btn"
          href="https://github.com/OliverVorasai"
          target="_blank"
          rel="noopener"
          aria-label="Github Link"
        >
          <fa-icon :icon="['fab', 'github']" class="mr-2"></fa-icon>GitHub
        </a>
        <a
          class="outline-btn"
          href="https://www.linkedin.com/in/olivervorasai/"
          target="_blank"
          rel="noopener"
          aria-label="Linkedin Link"
        >
          <fa-icon :icon="['fab', 'linkedin']" class="mr-2 linkedin"></fa-icon
          >LinkedIn
        </a>
        <a
          class="outline-btn"
          href="mailto:olivervorasai@gmail.com"
          aria-label="Email Link"
        >
          <fa-icon :icon="['fas', 'at']" class="mr-2"></fa-icon>Email
        </a>
      </div>
    </section>
  </div>
</template>

<style scoped lang="postcss">
.nav-btn {
  @apply py-2 px-2 m-1 rounded;
}
.nav-btn:hover {
  @apply text-blue-500 bg-gray-300;
}
.outline-btn {
  @apply py-2 px-4 mx-1 my-4 rounded border;
}
.outline-btn:hover {
  @apply border-gray-700;
}

.linkedin {
  color: #2867b2;
}
</style>
