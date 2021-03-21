<template>
  <div class="container px-2">
    <!-- Feature -->
    <section class="flex flex-col text-center my-12">
      <h1 class="text-6xl leading-none md:leading-normal">Oliver Vorasai</h1>
      <h2 class="text-4xl text-gray-700">Front End Developer</h2>
      <div class="flex flex-row justify-center">
        <a
          class="outline-btn"
          href="https://github.com/OliverVorasai"
          target="_blank"
          rel="noopener"
          aria-label="Github Link"
        >
          <img
            :src="require('@/assets/icons/github.svg')"
            class="inline-block align-top w-6 mr-2"
            aria-hidden="true"
          />GitHub
        </a>
        <a
          class="outline-btn"
          href="https://www.linkedin.com/in/olivervorasai/"
          target="_blank"
          rel="noopener"
          aria-label="Linkedin Link"
        >
          <img
            :src="require('@/assets/icons/linkedin.svg')"
            class="inline-block align-top w-6 mr-2"
            aria-hidden="true"
          />LinkedIn
        </a>
        <a
          class="outline-btn"
          href="mailto:olivervorasai@gmail.com"
          aria-label="Email Link"
        >
          <img
            :src="require('@/assets/icons/at.svg')"
            class="inline-block align-top w-6 mr-2"
            aria-hidden="true"
          />Email
        </a>
      </div>
    </section>

    <!-- Websites -->
    <section id="websites-section" class="my-12">
      <h1 class="text-5xl mx-2 font-semibold">Websites</h1>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <card v-for="(website, index) in websites" :key="index">
          <h2 class="text-center text-4xl">
            {{ website.title }}
          </h2>
          <a
            :href="website.url"
            target="_blank"
            rel="noopener"
            :aria-label="'Link to ' + website.title"
          >
            <img
              class="rounded-xl hover:filter-darken"
              :src="website.image"
              :alt="website.title + ' website screenshot'"
            />
          </a>
        </card>
      </div>
    </section>

    <!-- Work -->
    <section id="work-section" class="my-12">
      <h1 class="text-5xl mx-2 font-semibold">Work</h1>
      <div class="grid grid-cols-1 md:grid-cols-2">
        <a
          v-for="(job, index) in work"
          :key="index"
          :href="job.url"
          target="_blank"
          rel="noopener"
          class="cell hover:filter-darken px-12 py-12"
        >
          <div>
            <h2 class="text-center text-4xl text-white">{{ job.title }}</h2>
            <img
              class="rounded-xl h-24 mx-auto my-6"
              :src="job.image"
              :alt="'Icon for ' + job.title"
            />
            <nuxt-content
              :document="job"
              class="text-center text-xl font-light text-white"
            ></nuxt-content>
          </div>
        </a>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const websites = await $content('websites').sortBy('rank', 'asc').fetch()
    const work = await $content('work').sortBy('createdAt', 'desc').fetch()

    return { websites, work }
  },
}
</script>

<style scoped lang="postcss">
/* Styles for button links */
.outline-btn {
  @apply py-2 px-4 mx-1 my-4 rounded border;
}
.outline-btn:hover {
  @apply border-gray-700;
}

/* Styles for work section */
.cell:nth-child(1) {
  @apply rounded-t-xl;
}
.cell:nth-child(n) {
  @apply col-span-2;
  background-color: #c1605c;
}
.cell:nth-child(2) {
  @apply col-span-2 bg-blue-800;
  @screen md {
    @apply col-span-1;
  }
}
.cell:nth-child(3) {
  @apply col-span-2 bg-blue-400;
  @screen md {
    @apply col-span-1;
  }
}
.cell:nth-last-child(1) {
  @apply rounded-b-xl;
}
</style>
