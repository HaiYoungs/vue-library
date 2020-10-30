<template>
    <div>
      <button
        class="ui-btn"
        :class="{
          'ui-btn-xsmall': xsmall,
          'ui-btn-small': small,
          'ui-btn-large': large,
          'ui-btn-xlarge': xlarge,
          'ui-btn-tile': tile,
          'ui-btn-rounded': rounded,
          'ui-btn-circle': circle,
        }"
        @click="onClickBtn"
      >
        <slot>Button</slot>
      </button>
    </div>
</template>

<script lang="ts">

import { Component, Vue, Emit, Prop } from 'vue-property-decorator';

@Component

export default class App extends Vue {

  @Prop(Boolean) private xsmall: boolean | undefined
  @Prop(Boolean) private small: boolean | undefined
  @Prop(Boolean) private large: boolean | undefined
  @Prop(Boolean) private xlarge: boolean | undefined
  @Prop(Boolean) private tile: boolean | undefined
  @Prop(Boolean) private rounded: boolean | undefined
  @Prop(Boolean) private circle: boolean | undefined

  @Emit('click') private emitClickEvent (e: MouseEvent) {
    console.log(e)
  }

  private mounted() {
    console.log(this.large)
  }

  private onClickBtn (e: MouseEvent) {
    this.emitClickEvent(e);
  }
}


</script>

<style scoped lang="stylus">
resize(minWidth, height, paddingLR, fontSize) {
  min-width: minWidth
  height: height
  padding: 0 paddingLR
  font-size: fontSize
}
.ui-btn {
  min-width 64px
  height 36px
  padding 0 16px
  border 0 solid black
  border-radius 4px
  font-size 0.875rem
  font-weight 500
  letter-spacing 0.09em
  outline none
  background-color #2D8CF0
  cursor pointer
  user-select none
}
.ui-btn-xsmall {
  resize(36px, 20px, 9px, 0.625rem)
}
  
.ui-btn-small {
  resize(50px, 28px, 12px, 0.75rem)
}
  
.ui-btn-large {
  resize(78px, 44px, 19px, 0.875rem)
}
  
.ui-btn-xlarge {
  resize(92px, 52px, 23px, 1rem)
}
.ui-btn-tile
  border-radius 0
.ui-btn-rounded
  border-radius (@height / 2)
</style>

