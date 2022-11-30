<template>
  <div class="app"></div>
  <post-form @create="createPost" />
  <post-list v-bind:posts="posts" @remove="removePost" />
  <!--  Короткая завпись v-bind: -->
  <!--  <post-list :posts="posts" />-->
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "js1", body: "des1" },
        { id: 2, title: "js2", body: "des2" },
        { id: 3, title: "js3", body: "des3" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => post.id !== p.id);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
