<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">

    <div>
      <button v-on:click="likes++">+</button>
      <button @click="likes--">-</button>
      <div>Likes: <strong>{{ likes }}</strong></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  data () {
    return {
      likes: 0
    }
  }
}
</script>
