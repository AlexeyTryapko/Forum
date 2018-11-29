<template>
  <form @submit.prevent="addPost">
    <div class="from-group">
      <textarea
        name=""
        rows="10"
        cols="30"
        class="form-input"
        v-model="text"
      >
      </textarea>
    </div>
    <div class="form-actions">
      <button class="btn-blue">Submit post</button>
    </div>
  </form>
</template>

<script>
export default {
  props: {
    threadId: {
      required: true,
      type: String,
    }
  },
  data() {
    return {
      text: '',
    }
  },
  methods: {
    addPost() {
      const postId = 'GreatePost' + Math.random();
      const post = {
        text: this.text,
        publishedAt: Math.floor(Date.now() / 1000),
        threadId: this.threadId,
        userId: "L664y3qZSubDbT1R6npC0EEybJ73",
        '.key': postId,
      };
      this.text = '';
      this.$emit('save', { post })
    },
  }
}
</script>
