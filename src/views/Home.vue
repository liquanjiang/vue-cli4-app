<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="你好，我是李大师"/>
    <Clock></Clock>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Clock from '@/components/Clock'

export default {
  name: 'home',
  components: {
    HelloWorld,
    Clock
  }
}
</script>
