<template>
  <div class="container">
    <img
      class="object-center mx-auto h-64 w-auto"
      :src="choiceImage"
      alt="404"
    />
    <h1 v-if="error.statusCode === 404">Page not found</h1>
    <h1 v-else>An error occurred</h1>
    <NuxtLink to="/">Back to Home</NuxtLink>
  </div>
</template>

<script>
export default {
  props: ['error'],
  data() {
    return {
      images: [
        require('~/assets/images/yotsuba.jpg'),
        require('~/assets/images/pdg.jpg'),
      ],
      choiceImage: null,
    }
  },
  mounted() {
    this.randomImage(this.images)
  },
  methods: {
    randomItem(items) {
      return items[Math.floor(Math.random() * items.length)]
    },
    randomImage(items) {
      const tmp = this.choiceImage
      this.choiceImage = this.randomItem(this.images)
      if (tmp === this.choiceImage) this.randomImage(items)
    },
  },
}
</script>
