<template>
  <div class="scroll-nav-container">
    <!-- <h1>This is an about ScrollNav</h1> -->
    <div class="left-nav-container" ref="navWrapper">
      <ul id="">
        <div class="nav-item" v-for="(item, index) in navList" :key="index">
          <div>
            {{ item.title }}
          </div>
        </div>
      </ul>
    </div>
    <div class="right-content-container" ref="contentWrapper">
      <ul>
        <div class="content-item " v-for="(item, index) in navList" :key="index" ref="contentItem">
          <div>{{ item.title + index }}</div>
        </div>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import BScroll from "better-scroll";

@Component
export default class ScrollNav extends Vue {
  @Prop() private msg!: string;
  private navList = [
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
    {
      title: "test",
      key: "1",
      list: [
        {
          title: "title",
          link: "2",
        },
      ],
    },
  ];
  private scrollY: any = 0;
  private navWrapper: any;
  private contentWrapper: any;
  private contentItemHeight: any = [];

  created() {
    this.$nextTick(() => {
      this.initScroll()
    })
  }

  initScroll() {
    this.navWrapper = new BScroll(this.$refs.navWrapper, {
      click: true,
    });

    this.contentWrapper = new BScroll(this.$refs.contentWrapper, {
      click: true,
      probeType: 3,
    });

    this.contentWrapper.on("scroll", (pos: { x: any; y: any }) => {
      console.log('=scroll===', pos)
      // 判断滑动方向，避免下拉时分类高亮错误（如第一分类商品数量为1时，下拉使得第二分类高亮）
      if (pos.y <= 0) {
        this.scrollY = Math.abs(Math.round(pos.y));
      }
    });
  }

  private calculateHeight() {
        let contentItemList = this.$refs.contentItem;
        let height = 0;
        this.contentItemHeight.push(height);
        for (let i = 0; i < contentItemList.length; i++) {
          let item = contentItemList[i];
          height += item.clientHeight;
          this.contentItemHeight.push(height);
        }
      };
// }
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
  // private onClick(): void {
  //   // window.alert(this.message)
  // }
}
</script>

<style lang="stylus" scoped>

.scroll-nav-container
  display flex
  position: absolute
  top: 174px
  bottom: 46px
  width: 100%
  overflow: hidden
  .left-nav-container
    flex 0 0 80px
    width 80px
    background #f5f5ff
    .nav-item
      height 150px
  .right-content-container
    flex 1
    .content-item 
      height 200px
      border 1px solid #cccccc
</style>
