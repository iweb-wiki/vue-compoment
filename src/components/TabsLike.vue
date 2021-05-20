<template>
  <div class="container">
    <div class="tabs">
      <div
        class="tab"
        :class="{ active: active === index }"
        v-for="(item, index) in [1, 2]"
        :key="index"
        @click="onClick(index)"
      >
        item
      </div>
    </div>
    <div class="content">
      <div class="wrap" :style="{ transform: `translateX(-${active * 100}%)` }">
        <div class="tab-con" :class="{ show: active === 0 }">
          <div class="cc">
            <div v-for="i in [1, 2]" :key="i">
              111
            </div>
          </div>
          <button>提交</button>
        </div>
        <div class="tab-con" :class="{ show: active === 1 }">
          <div class="cc">
            <div v-for="(i, index) in [1, 2, 2, 2, 2, 2, 2, 2]" :key="index">
              222
            </div>
          </div>
          <button>提交</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

// tabs 内容同高，按钮显示在最下边
@Component
export default class App extends Vue {
  active!: number;
  data() {
    return {
      active: 0,
    };
  }
  onClick(index: number) {
    this.active = index;
  }
}
</script>

<style lang="stylus" scoped>
.container
  width 300px
  margin 0 auto
.tabs
  display flex
  justify-content space-around
  border  1px solid pink
.tab
  cursor pointer
  flex 1
  &.active
    background-color #ccc
  &:hover
    background-color #ccc
.content
  overflow hidden
.wrap
  display flex
  flex-direction row
  flex-basis 100%
  flex 0 0 100%
.tab-con
  background-color #ddd
  flex 0 0 100%
  display flex
  flex-direction column
.cc
  flex 1
</style>
