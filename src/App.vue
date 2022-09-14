<template>
  <tr>
    <th>ID</th>
    <th>User ID</th>
    <th>Title</th>
    <th>Body</th>
  </tr>
  <div :key="post.id" v-for="post in posts">
    <TableRow :post="post" />
  </div>
</template>

<script>
import TableRow from "./components/TableRow.vue"
export default {
  name: "App",
  components: {TableRow},
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    async fetchPosts() {
      const res = await fetch("https://jsonplaceholder.typicode.com/posts");
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
