<template>
  <div>Hello world</div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    async fetchPosts() {
      const res = await fetch('https://jsonplaceholder.typicode.com/posts');
      const data = await res.json();
      console.log(data);
      return data;
    },
  },
  async created() {
    this.posts = await this.fetchPosts();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
