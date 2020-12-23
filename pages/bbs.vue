<template>
  <div id="bbs" class="common_contents_wrap">
    <h2>BBS</h2>
    <p class="">
      キリ番報告はこちらから♪<br />
      他にも管理人KIICHIへのご意見・ご要望など自由にカキコしてください(*´∀｀)<br />
      以下のような荒らしは絶対禁止です！<br />
    </p>
    <ul>
      <li>下ネタや誹謗・中傷ネタの投稿</li>
      <li>「○○するだけでお金がもらえる」のような書き込み</li>
      <li>マナーの悪い書き込み</li>
      <li>その他管理人が不適切と判断した記事の投稿</li>
    </ul>
    <!-- 投稿フォーム -->
    <div class="bbs_form_wrap">
      <div class="bbs_form">
        <form @submit.prevent="postBBS">
          <p>
            <label for="name">名前</label>
            <input id="name" v-model="inputName" type="text" />
          </p>
          <p>
            <label for="title">件名</label>
            <input id="title" v-model="inputTitle" type="text" />
          </p>
          <p>
            <label for="body">本文</label>
            <span class="force_color"></span>
            <textarea id="body" v-model="inputBody" required></textarea>
          </p>
          <p>
            <input type="submit" value="カキコ" />
            <input type="reset" value="リセット" />
          </p>
        </form>
      </div>
    </div>

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
  data() {
    return {
      bbsPosts: [],
      inputName: null,
      inputTitle: null,
      inputBody: null,
    }
  },
})
</script>

<style></style>
