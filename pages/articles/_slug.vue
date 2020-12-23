<template>
  <div>
    {{ article.title }}
    <nuxt-content :document="article" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  components: {},
  async asyncData({ $content, params }) {
    const article = await $content(`articles/${params.slug}`).fetch()

    return {
      article,
    }
  },
})
</script>
