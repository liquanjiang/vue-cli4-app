<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="你好，我是李大师"/>
    <Clock></Clock>
    <Test :test="test" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import Clock from '@/components/Clock';
import Test from '@/components/Test';

export default {
  name: 'home',
  data () {
    return {
      test: {
        name: '李大师123',
        key: '123',
        value: 30
      }
    };
  },
  components: {
    HelloWorld,
    Clock,
    Test
  }
};
</script>
