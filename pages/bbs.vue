<template>
  <div>
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
    <bbs-post-form />
    <bbs-get-form />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import bbsGetForm from '~/components/bbs-get-form.vue'
import bbsPostForm from '~/components/bbs-post-form.vue'

export default Vue.extend({
  components: {
    bbsGetForm,
    bbsPostForm,
  },
})
</script>

<style></style>
