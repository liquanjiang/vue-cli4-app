<template>
  <div class="clock">
    <h4>今天是{{ time }}</h4>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import moment from 'moment';

@Component
export default class Clock extends Vue {
  time: string = '';
  timer: any = null;
  constructor () {
    super();
    this.time = moment().format('今天是YYYY年MM月DD日， 现在时刻HH:mm:ss');
  }

  mounted ():void {
    this.change();
    const date = moment().subtract(3, 'day').unix();
    console.log(date);
    console.log(moment().unix());
  }

  change ():void {
    this.timer = setInterval(() => {
      this.time = moment().format('今天是YYYY年MM月DD日， 现在时刻HH:mm:ss');
    }, 1000);
  }

  destroyed ():void {
    clearInterval(this.timer);
  }
}
</script>

<style scoped></style>
