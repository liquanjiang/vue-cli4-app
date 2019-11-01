<template>
  <div class="clock">
    <h4>{{ time }}</h4>
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
    this.time = moment().format('YYYY-MM-DD HH:MM:SS');
  }

  mounted () {
    this.change();
  }

  change () {
    this.timer = setInterval(() => {
      this.time = new Date().toLocaleString();
    }, 1000);
  }

  destroyed () {
    clearInterval(this.timer);
  }
}
</script>

<style scoped></style>
