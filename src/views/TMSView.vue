<script setup lang="ts">
  import {ref} from "vue";
  import Axios from "axios";  

  const message = ref("未送信");
  const user_id = ref();
  const password = ref();
  const password_conf = ref();
  const name = ref();
  const onFormSubmit = (): void => {
    message.value = "送信されました"
    console.log(password.value);
    
    Axios.post("http://localhost:3001/users", {
      user: {
        user_id: user_id.value,
        password: password.value,
        password_confirmation: password_conf.value,
        name: name.value
      }
    })
    .then(function(res){
      console.log(res)
    })
    .catch(function(err){
      console.log(err.message)
    });
  }
  
</script>

<template>
  <form v-on:submit.prevent="onFormSubmit">
    <p>ログインID</p>
    <input type="text" v-model="user_id">
    <p>名前</p>
    <input type="text" v-model="name">
    <p>パスワード</p>
    <input type="password" v-model="password">
    <input type="password" v-model="password_conf">
    <button type="submit">新規作成</button>
  </form>

  <p>{{user_id}}</p>
  <p>{{password}}</p>
  <p>{{name}}</p>
  <p>{{message}}</p>
  
</template>

<style>

</style>
