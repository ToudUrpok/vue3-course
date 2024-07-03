<template>
  <div
    v-if="posts.length"
    class="post-list"
  >
    <h2>{{ listTitle }}</h2>

    <PostCard
      v-for="post in posts"
      :key="post.id"
      :post=post
      @remove="$emit('remove', $event)"
    />
  </div>
  <h2
    v-else
  >
    There are no posts for now ...
  </h2>
</template>

<script>
import PostCard from './PostCard.vue'

export default {
  components: {
    PostCard
  },
  props: {
    posts: {
      type: Array,
      default: () => []
    }
  },
  computed: {
    listTitle () {
      const pluralised = this.posts.length === 1 ? 'Post' : 'Posts'
      return `${this.posts.length} ${pluralised}`
    }
  }
}
</script>

<style scoped>
.post-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>
