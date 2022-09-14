<template>
  <tr>
    <td>{{post.id}}</td>
    <td>{{post.userId}}</td>
    <td class="title">{{post.title}}</td>
    <td class="body">{{post.body}}</td>
  </tr>
</template>

<script>
export default {
  name: "TableRow",
  props: ["post"],
};
</script>

<style>
.title {
    max-width: 5em;
    min-width: 5em;
}
.body {
    max-width: 30em;
    text-align: left;
}
</style>