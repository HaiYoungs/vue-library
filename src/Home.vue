<template>
    <div class="root-home">
      Home
      <div class="btn-container">
        <UIButton @click="onClick"
          :xsmall="xsmall"
          :small="small"
          :large="large"
          :xlarge="xlarge"
          :tile="tile"
          :rounded="rounded"
          :circle="circle"
        >点我呀</UIButton>
      </div>
      <div class="btn-group">
        <UIButton class="btn" @click="resize('xsmall')">超小</UIButton>
        <UIButton class="btn" @click="resize('small')">小</UIButton>
        <UIButton class="btn" @click="resize('normal')">正常</UIButton>
        <UIButton class="btn" @click="resize('large')">大</UIButton>
        <UIButton class="btn" @click="resize('xlarge')">超大</UIButton>
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
  private tile = false;
  private rounded = false;
  private circle = false;

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

  private changeRadius(name: string) {
    switch (name) {
      case 'tile':
        this.tile = true;
        this.rounded = false;
        this.circle = false;
        break;
      case 'rounded':
        this.tile = false;
        this.rounded = true;
        this.circle = false;
        break;
      case 'circle':
        this.tile = false;
        this.rounded = false;
        this.circle = true;
        break;
    
      default:
        break;
  }

  private onClick(e: MouseEvent) {
    console.log(e);
  }
}
</script>

<style scoped lang="stylus">
.btn-container {
  width 480px
  height 160px
  display flex
  justify-content center
  align-items center
  margin 0 auto

.btn-group
  text-align center
  margin-bottom 15px

.btn
  display inline-block
  margin-right 15px

>>>>>>> f010968ac0fa5ab9f35e35e92674052fe09aee81
</style>
