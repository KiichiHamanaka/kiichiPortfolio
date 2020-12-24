<template>
  <v-navigation-drawer app>
    <v-list>
      <v-list-item v-for="url in urlList" :key="url.title">
        <v-list-item-avatar></v-list-item-avatar>
        <v-list-item-content>
          <nuxt-link :to="url.path">{{ url.title }}</nuxt-link>
        </v-list-item-content>
      </v-list-item>
    </v-list>
    <iframe
      style="background-color: transparent"
      width="135"
      height="210"
      src="https://weep.jp/embed/harbot/"
    >
    </iframe>
  </v-navigation-drawer>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      urlList: [
        {
          title: 'TOP',
          path: '/',
        },
        {
          title: 'ABOUT',
          path: '/about',
        },
        {
          title: 'PROFILE',
          path: '/profile',
        },
        {
          title: 'WORKS',
          path: '/works',
        },
        {
          title: 'BBS',
          path: '/bbs',
        },
        {
          title: 'BLOG',
          path: '/blog',
        },
        {
          title: 'LINKS',
          path: '/links',
        },
      ],
    }
  },
})
</script>

<style>
iframe {
  border-width: 0px;
}
</style>
