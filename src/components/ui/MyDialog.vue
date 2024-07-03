<template>
  <div
    v-show="show"
    class="dialog-wrapper"
    @click="hide"
  >
    <div
      @click.stop
      class="dialog"
    >
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyDialog',
  props: {
    show: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    hide () {
      this.$emit('update:show', false)
    }
  }
}
</script>

<style scoped>
.dialog-wrapper {
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  background: rgba(0,0,0,0.5);
  position: fixed;
  display: flex;
}

.dialog {
  margin: auto;
  background: white;
  border-radius: 15px;
  min-height: 100px;
  min-width: 350px;
}
</style>
