<template>
  <div class="home">
    <HelloWorld msg="WE ARE MAKING A PROKECT"/>
    <ChatBot/>
  </div>
</template>

<script>

import HelloWorld from '@/components/HelloWorld.vue'
import ChatBot from '@/components/ChatBot.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    ChatBot
  }
}
</script>
