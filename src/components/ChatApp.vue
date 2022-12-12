<template>
  <div class="chat">
    <chat-title :fio="fio" :post="post" />
    <messages-list :messages="messages" />
    <message-box @sendMessage="addMessage" />
  </div>
</template>

<script>
import ChatTitle from "./chat/ChatTitle.vue";
import MessagesList from "./chat/MessagesList.vue";
import MessageBox from "./chat/MessageBox.vue";
export default {
  name: "ChatApp",
  data() {
    return {
      fio: "Pitter Morgan",
      post: "Frontend developer",
      messages: [],
    };
  },
  components: {
    ChatTitle,
    MessagesList,
    MessageBox,
  },
  methods: {
    addMessage(message) {
      this.messages.push(message);
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/chat.scss";
</style>
