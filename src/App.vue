<template>
  <div id="container">
    <tr>
      <th>ID</th>
      <th>User ID</th>
      <th id="title">Title</th>
      <th>Body</th>
    </tr>
    <div :key="post.id" v-for="post in posts">
      <TableRow :post="post" />
    </div>
  </div>
</template>

<script>
import TableRow from "./components/TableRow.vue";
export default {
  name: "App",
  components: { TableRow },
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    async fetchPosts() {
      const res = await fetch("https://jsonplaceholder.typicode.com/posts");
      const data = await res.json();
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
#container {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
th,
td {
  padding-top: 10px;
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 40px;
}
</style>
