<template>
  <div class="text">
    <p> {{test.name}}</p>
    <p> {{value}}</p>
    <div>
      <label>
        <input type="text"  @input="change" :value="FatherValue">
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
  private value: string | undefined = '111';
  @Prop() @Model('tooWay-binding') FatherValue: string | undefined;
  @Emit()
  private changeValue (value:string) {
    return value;
  }

  @Watch('FatherValue')
  private onchange (newValue:string, oldValue:string):void {
    console.log(newValue, oldValue);
  }

  private change (e:any):void {
    this.$emit('tooWay-binding', e.target.value);
    this.changeValue(e.target.value);
  }

  mounted (): void {

  }

  destroyed (): void {

  }
}
</script>

<style scoped>

</style>
