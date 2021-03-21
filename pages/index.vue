<template>
  <div class="container px-2">
    <!-- Navigation -->
    <nav class="flex justify-center">
      <a class="nav-btn" href="#websites-section">Websites</a>
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
          <fa-icon
            :icon="['fab', 'linkedin']"
            class="mr-2 text-blue-700"
          ></fa-icon
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

    <!-- Websites -->
    <section id="websites-section">
      <h1 class="text-5xl mx-2">Websites</h1>
      <div class="grid grid-cols-2 gap-4">
        <card v-for="(website, index) in websites" :key="index">
          <h2 class="text-center">{{ website.title }}</h2>
          <a :href="website.url" target="_blank" rel="noopener">
            <img class="rounded-xl hover:filter-darken" :src="website.image" />
          </a>
        </card>
      </div>
    </section>

    <!-- Work -->
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const websites = await $content('websites')
      .sortBy('createdAt', 'desc')
      .fetch()

    return { websites }
  },
}
</script>

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
</style>
