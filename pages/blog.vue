<template>
  <div>
    <h1>貴一のブログ</h1>
    <!-- カードのコンポーネントにしたい -->
    <div v-for="article in articles" :key="article">
      <div class="card">
        <img class="card-img" :src="getImage(article.image)" alt="title" />
        <nuxt-link :to="article.path">
          {{ article.title }}
          {{ article.createdAt }}
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  async asyncData({ $content }) {
    const articles = await $content('articles').limit(20).fetch()
    return {
      articles,
    }
  },
  methods: {
    getImage(image: string) {
      const imagePath: string = image || '@/assets/images/noImage.jpg'
      return {
        imagePath,
      }
    },
  },
})
</script>

<style></style>
