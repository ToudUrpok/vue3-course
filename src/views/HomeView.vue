<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">

    <MyButton
      @click="showDialog=true"
    >
      Create Post
    </MyButton>

    <MyDialog
      v-model:show="showDialog"
    >
      <PostForm
        @create="createPost"
      />
    </MyDialog>

    <PostList
      :posts="posts"
      @remove="removePost"
      class="posts-list"
    />
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue'
import PostForm from '@/components/PostForm.vue'

export default {
  name: 'HomeView',
  components: {
    PostList,
    PostForm
  },
  data () {
    return {
      posts: [],
      showDialog: false
    }
  },
  methods: {
    createPost (post) {
      post.id = Date.now()
      this.posts.push(post)
      this.showDialog = false
    },
    removePost (postId) {
      this.posts = this.posts.filter(p => p.id !== postId)
    }
  }
}
</script>

<style scoped>
.home {
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
}

.posts-list {
  width: 80%;
}
</style>
