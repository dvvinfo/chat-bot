<template>
  <div class="message new" :class="{ loading: loading }">
    <figure class="avatar">
      <img src="@/assets/img/1.jpg" alt="avatar" />
    </figure>
    <span>{{ message.text }}</span>
    <div class="timestamp">{{ dateTime }}</div>
  </div>
</template>

<script>
export default {
  name: "ChatbotMessage",
  props: {
    message: Object,
  },
  data() {
    return {
      loading: true,
    };
  },
  created() {
    setTimeout(() => {
      this.loading = false;
    }, 1000 + Math.random() * 20 * 100);
  },
  computed: {
    dateTime() {
      const { date } = this.message;
      const hours = date.getHours().toString().padStart(2, "0");
      const minutes = date.getMinutes().toString().padStart(2, "0");
      return `${hours}:${minutes}`;
    },
  },
};
</script>

<style></style>
