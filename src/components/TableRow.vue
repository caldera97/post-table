<template>
  <tr>
    <td>{{post.id}}</td>
    <td>{{post.userId}}</td>
    <td>{{post.title}}</td>
    <td>{{post.body}}</td>
  </tr>
</template>

<script>
export default {
  name: "TableRow",
  props: ["post"],
};
</script>