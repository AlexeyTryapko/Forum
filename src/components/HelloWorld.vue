<template>
  <div>
    <h1>Welcome to Forum</h1>
    <div v-for="thread in threads">
      <h2>{{ thread.title }}</h2>
      <div v-for="postId in thread.posts">
        <h3>{{ users[posts[postId].userId].name }}</h3>
        <p>{{ posts[postId].text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data';

export default {
  name: 'HelloWorld',
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users,
    }
  }
}
</script>
