<template>
  <div class="home">
    <HelloWorld msg="你好，我是李大师"/>
    <Clock></Clock>
    <Test :test="test" @changeValue="change" v-model="FatherValue"></Test>
    <div>{{FatherValue}}</div>
    <Data :data="FatherValue" value></Data>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import Clock from '@/components/Clock';
import Test from '@/components/Test';
import Data from '@/components/Data';

export default {
  name: 'home',
  data () {
    return {
      test: {
        name: '李大师123',
        key: '123',
        value: 30
      },
      FatherValue: 100
    };
  },
  components: {
    HelloWorld,
    Clock,
    Test,
    Data
  },

  methods: {
    change (e) {
      console.log(e);
    }
  }
};
</script>
