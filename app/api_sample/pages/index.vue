<template>
  <div>
  <h1>API</h1>
  {{sample}}{{info}}
  <h1>GitHubユーザー情報</h1>
  <ul>
    <li>名前 : {{user.name}}</li>
    <li><a v-bind:href="user.html_url">GitHubへ</a></li>
    <li>公開しているリポジトリ : {{user.public_repos}}個</li>
    <li>Bio : {{user.bio}}</li>
  </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios';

export default Vue.extend({
  data(){
    return{
      sample : "Nuxt.js + ",
      info: "API",
      user: []
    }
  },
  created(){
    axios.get('https://api.github.com/users/You-saku')
          .then(response => this.user = response.data);
  }
})
</script>
