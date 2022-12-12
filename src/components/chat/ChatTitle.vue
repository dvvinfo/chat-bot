<template>
  <div class="chat-title">
    <h1>{{ fio }}</h1>
    <h2>{{ post }}</h2>
    <figure class="avatar">
      <img src="@/assets/img/1.jpg" alt="avatar" />
    </figure>
  </div>
</template>

<script>
export default {
  name: "ChatTitle",
  props: {
    fio: {
      type: String,
      default: "",
    },
    post: {
      type: String,
      default: "",
    },
  },
};
</script>

<style></style>
