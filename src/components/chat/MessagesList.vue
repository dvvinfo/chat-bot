<template>
  <div class="messages">
    <div class="messages-content" ref="scrollbar">
      <template v-for="message in messages">
        <chatbot-message
          v-if="message.chatbot"
          :key="message.id"
          :message="message"
        />
        <person-message v-else :key="message.id" :message="message" />
      </template>
    </div>
  </div>
</template>

<script>
import PersonMessage from "./messages/PersonMessage.vue";
import ChatbotMessage from "./messages/ChatbotMessage.vue";
export default {
  name: "MessagesList",
  components: {
    PersonMessage,
    ChatbotMessage,
  },
  props: {
    messages: Array,
  },
  watch: {
    messages() {
      this.$nextTick(this.scrollToBottom());
    },
  },
  methods: {
    scrollToBottom() {
      this.$refs.scrollbar.scrollTop = this.$refs.scrollbar.scrollHeight;
    },
  },
};
</script>

<style></style>
