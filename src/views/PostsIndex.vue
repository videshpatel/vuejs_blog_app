<template>
  <div class="container">
    <h1>All Posts</h1>
    <div v-for="post in posts">
      <h2>{{ post.user_id }}</h2>
      <h2>{{ post.title }}</h2>
      <h2>{{ post.body }}</h2>
      <h2>{{ post.image }}</h2>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data: function() {
    return {
      posts: []
    };
  },
  created: function() {
    axios.get("/api/posts").then(response => {
      this.posts = response.data;
    });
  },
  methods: {}
};
</script>
