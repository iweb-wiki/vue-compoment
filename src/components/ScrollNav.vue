<template>
  <div class="scroll-nav-container">
    <h1>This is an about ScrollNav</h1>
    <div class="left-nav-container">
      <div v-for="(item, index) in navList" :key="index"  >
        <div id="">
          {{ item.title }}
        </div>
      </div>
    </div>
    <div class="right-content-container">
      <div v-for="(item, index) in navList" :key="index">
        <div>{{item.title + index}}</div>
      </div>
    </div>
  </div>
</template>

<script lang='ts'>
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class ScrollNav extends Vue {
  // @Prop() private msg!: string;
  private navList = [
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
    {
      title: 'test',
      key: '1',
      list: [
        {
          title: 'title',
          link: '2',
        },
      ],
    },
  ];

  // static data: {
  //   navList: [
  //     {
  //       title: '2',
  //     },
  //   ],
  // }
  // private name() {
  //   console.log('====');
  // }
  private onClick(): void {
    // window.alert(this.message)
  }

}

</script>


<style lang="stylus" scoped>

.scroll-nav-container 
  display flex  
  .left-nav-container
    flex 0 0 80px;
    width 80px;
  .right-content-container
    flex 1
</style>