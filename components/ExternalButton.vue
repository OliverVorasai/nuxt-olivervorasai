<template>
  <a
    class="outline-btn"
    :href="link"
    target="_blank"
    rel="noopener"
    :aria-label="'Link to ' + text"
  >
    <img :src="icon" class="w-4 md:w-6" aria-hidden="true" />
    <div>{{ text }}</div>
  </a>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: () => '',
    },
    icon: {
      type: String,
      default: () => '',
    },
    link: {
      type: String,
      default: () => '',
    },
  },
}
</script>

<style scoped lang="postcss">
.outline-btn {
  @apply flex gap-2 px-2 items-center py-1 mx-1 my-4 rounded border;
  @screen md {
    @apply px-4 py-2;
  }
}
.outline-btn:hover {
  @apply border-gray-700;
}
</style>
