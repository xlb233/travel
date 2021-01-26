<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-image"><img class="icon-img-content" :src="item.imgUrl" ></div>
            <p class="icon-desc">{{ item.desc }}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        loop: false,
        autoplay: false
      },
      iconList: [{
        id: '0001',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '热门景点'
      }, {
        id: '0002',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '滑雪季'
      }, {
        id: '0003',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '泡温泉'
      }, {
        id: '0004',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '动植物园'
      }, {
        id: '0005',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '一日游'
      }, {
        id: '0006',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '必游榜单'
      }, {
        id: '0007',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '自然风光'
      }, {
        id: '0008',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '全部'
      }, {
        id: '0009',
        imgUrl: `http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20209/7c1e26fd490c3b65c2858fe5da96141c.png`,
        desc: '购物'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang='stylus' scoped>
  @import '~styles/variables.styl';
  @import '~styles/mixins.styl';
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-image
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
  .icon-desc
    ellipsis()
    position: absolute
    bottom: 0
    left: 0
    right: 0
    height: .44rem
    line-height: .44rem
    color: $darkTextColor
    text-align: center
</style>
