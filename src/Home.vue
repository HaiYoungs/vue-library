<template>
  <div class="root-home">
    Home
    <div class="btn-container">
      <UIButton @click="onClick" :xsmall="xsmall" :small="small" :large="large" :xlarge="xlarge">点我呀</UIButton>
    </div>
    <div class="btn-group">
      <UIButton @click="resize('xsmall')">超小</UIButton>
      <UIButton @click="resize('small')">小</UIButton>
      <UIButton @click="resize('normal')">正常</UIButton>
      <UIButton @click="resize('large')">大</UIButton>
      <UIButton @click="resize('xlarge')">超大</UIButton>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import UIButton from "@/components/UIkit/UIButton.vue";

@Component({
  components: {
    UIButton
  }
})
export default class App extends Vue {
  private xsmall = false;
  private small = false;
  private large = false;
  private xlarge = false;

  private resize(name: string) {
    switch (name) {
      case "xsmall":
        this.xsmall = true;
        this.small = false;
        this.large = false;
        this.xlarge = false;
        break;
      case "small":
        this.xsmall = false;
        this.small = true;
        this.large = false;
        this.xlarge = false;
        break;
      case "normal":
        this.xsmall = false;
        this.small = false;
        this.large = false;
        this.xlarge = false;
        break;
      case "large":
        this.xsmall = false;
        this.small = false;
        this.large = true;
        this.xlarge = false;
        break;
      case "xlarge":
        this.xsmall = false;
        this.small = false;
        this.large = false;
        this.xlarge = true;
        break;

      default:
        break;
    }
  }

  private onClick(e: MouseEvent) {
    console.log(e);
  }
}
</script>

<style scoped lang="stylus">
.btn-container {
  width: 480px;
  height: 160px;
  // background-color red
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
