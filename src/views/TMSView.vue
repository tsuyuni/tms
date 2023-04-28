<script setup lang="ts">
  import {ref} from "vue";
  import Axios from "axios";

  

  const message = ref("未送信");
  const user_id = ref();
  const password = ref();
  const onFormSubmit = (): void => {
    message.value = "送信されました"
    
    Axios.post(
      "http://localhost:3001/users",
      {
        user_id: user_id.value,
    })
    .then(function(res){
      console.log(res)
    })
    .catch(function(err){
      console.log(err.response.data)
    });
  }
  
</script>

<template>
  <form v-on:submit.prevent="onFormSubmit">
    <p>ログインID</p>
    <input type="text" name="user_id" v-model="user_id">
    <p>パスワード</p>
    <input type="password" name="password" v-model="password">
    <button type="submit">新規作成</button>
  </form>

  <p>{{user_id}}</p>
  <p>{{password}}</p>
  <p>{{message}}</p>
  
</template>

<style>

</style>
