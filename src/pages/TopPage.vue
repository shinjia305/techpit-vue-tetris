<script lang="ts" setup>
  import { reactive } from "vue";

  const state = reactive({ lastname: "", firstname: "" });
  const startGame = () => {
    alert(`ユーザー名: ${ state.lastname }${ state.firstname }`)
  }
</script>

<template>
  <h1>トップ画面</h1>
  <p>{{ state.lastname }}{{ state.firstname }}</p>
  <input
    v-model="state.lastname"
    placeholder="苗字を入力してください（10文字以内）"
    maxlength="10"
  ><br>
  <input
    v-model="state.firstname"
    placeholder="名前を入力してください（10文字以内）"
    maxlength="10"
  >
  <br>
  <button v-on:click="startGame()">
    ゲームスタート！
  </button>
</template>

<style scoped>
  input {
    width: 18em;
    font-size: 1.1em;
    text-align: center;
  }

  p {
    font-size: 1.6em;
    font-weight: bold;
    height: 5vh;
  }
</style>
