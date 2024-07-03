<template>
  <input
    :value="modelValue"
    @input="updateInput"
    type="text"
  />
</template>

<script>
export default {
  name: 'MyInput',
  props: {
    modelValue: [String, Number]
  },
  methods: {
    updateInput (event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>

<style scoped>
input {
  border: 1px solid #2c3e50;
  border-radius: 10px;
  padding: 10px 15px;
  color: #2c3e50;
}
</style>
