<template>
  <form
    @submit.prevent
    class="create-post-form"
  >
    <h2>Create Post Form</h2>

    <MyInput
      v-model.trim="post.title"
      type="text"
      placeholder="Title"
    />

    <MyInput
      v-model.trim="post.body"
      type="text"
      placeholder="Content"
    />

    <div class="create-post-form-btns">
      <MyButton
        @click="createPost"
      >
        Create
      </MyButton>
    </div>
  </form>
</template>

<script>
export default {
  data () {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost () {
      this.$emit('create', {
        title: this.post.title,
        body: this.post.body
      })
      this.resetPost()
    },
    resetPost () {
      this.post.title = ''
      this.post.body = ''
    }
  }
}
</script>

<style scoped>
.create-post-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding: 50px;
  background-color: #7bbda053;
  border-radius: 15px;
}

.create-post-form-btns {
  padding: 5px;
  display: flex;
  justify-content: end;
}
</style>
