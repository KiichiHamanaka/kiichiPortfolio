<template>
  <!-- 投稿フォーム -->
  <div class="bbs_form_wrap">
    <!-- 掲示板フォーム -->
    <ul class="post_list">
      <li v-for="bbsPost in bbsPosts" :key="bbsPost.id" class="post_wrap">
        <div class="post_counts">
          <h4>
            {{ bbsPost.title }}
          </h4>
          <p class="bbs_txt">{{ bbsPost.body }}</p>
          <div class="bbs_detail">
            <p>
              <span>投稿者：{{ bbsPost.name }}</span>
              <span>投稿日：{{ bbsPost.date }}</span>
            </p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  methods: {
    getBBS() {
      // TODO: AWS上からデータを取得するためのメソッド
    },
  },
  data() {
    return {
      bbsPosts: [],
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
