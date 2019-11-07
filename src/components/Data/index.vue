<template>
  <div class="data">
    {{data}}
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';

@Component
export default class Data extends Vue {
  @Prop() data:string | undefined;
  mounted (): void {

  }

  destroyed (): void {

  }
}
</script>

<style scoped>
.data {
  width:200px;
  height:200px;
  background:#f1f1f1;
}
</style>
