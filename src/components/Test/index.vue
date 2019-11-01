<template>
  <div class="text">
    <p> {{test.name}}</p>
    <p> {{value}}</p>
    <div>
      <label>
        <input type="text" v-model="value">
      </label>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop, Model, Watch, Emit, Inject, Provide } from 'vue-property-decorator';

@Component
export default class Test extends Vue {
  @Prop({ type: Object }) private test: {
    name:string,
    key:string,
    value:number } | undefined;
  @Prop({ type: String }) private name: string | undefined;
  @Model() public value: string | undefined;

  @Watch('value')
  onchange (newValue:string, oldValue:string):void {
    console.log(newValue, oldValue);
  }

  mounted (): void {

  }

  destroyed (): void {

  }
}
</script>

<style scoped>

</style>
