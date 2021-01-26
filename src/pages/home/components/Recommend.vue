<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{ item.title }}</p>
          <p class="item-desc">{{ item.desc }}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: `http://img1.qunarzz.com/sight/p0/1410/23/8cf426aa573a841c41609aeaafa26fc7.jpg_200x200_aff8290b.jpg`,
        title: '汉拿山汤泉国际酒店（亚运村店）',
        desc: '带来浓郁的温泉洗浴文化和超值的精神享受'
      }, {
        id: '0002',
        imgUrl: `http://img1.qunarzz.com/sight/p0/2012/a3/a308c49c32b9084ba3.img.jpg_200x200_491cc4d7.jpg`,
        title: '渔阳滑雪场',
        desc: '带来浓郁的滑雪文化和超值的滑雪享受'
      }, {
        id: '0003',
        imgUrl: `http://img1.qunarzz.com/sight/p0/2010/ea/ea45e52a4e22851ca3.img.jpg_200x200_df8ffdaf.jpg`,
        title: '北京欢乐谷',
        desc: '带来浓郁的欢乐文化和超值的欢乐享受'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl';
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        ellipsis()
        line-height: .54rem
        font-size: .32rem
      .item-desc
        ellipsis()
        line-height: .4rem
        color: #ccc
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
