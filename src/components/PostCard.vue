<template>
  <div
    class="post-card"
  >
    <div class="post-card-content">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>

    <div class="post-card-btns">
      <MyButton
        @click="$emit('remove', post.id)"
      >
        remove
      </MyButton>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post-card {
  padding: 20px;
  background-color: #7bbda053;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.post-card-btns {
  padding: 5px;
  display: flex;
  justify-content: end;
}

.post-card-content {
  text-align: left;
}
</style>
