<template>
  <button>
    <slot/>
  </button>
</template>

<script>
export default {
  name: 'MyButton'
}
</script>

<style scoped>
button {
  padding: 10px 15px;
  background-color: #42b983;
  color: #2c3e50;
  font-weight: bold;
  border: none;
  border-radius: 10px;
  cursor: pointer;
}
</style>
