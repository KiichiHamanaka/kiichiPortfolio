<template>
  <div>
    <form @submit.prevent="postBBS">
      <label for="name">名前</label>
      <input id="name" v-model="name" type="text" />
      <label for="title">件名</label>
      <input id="title" v-model="title" type="text" />
      <label for="body">本文</label>
      <span class="force_color"></span>
      <textarea id="body" v-model="body" required></textarea>
      <input type="submit" value="書き込み" />
    </form>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  methods: {
    postBBS() {
      // TODO: AWS上にデータをポストするためのメソッド
    },
  },
  data() {
    return {
      name: null,
      title: null,
      body: null,
    }
  },
})
</script>

<style>
.top-table {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
