<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <router-link
        tag="li"
        class="border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/' + item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
  // data () {
  //   return {
  //     recommendList: [{
  //       id: '0001',
  //       imgUrl: 'http://img1.qunarzz.com/sight/source/1505/f1/ae9d4299b8aaea.jpg_r_640x214_0c555905.jpg',
  //       title: '南京阅江楼',
  //       desc: '南京阅江楼南京阅江楼南京阅江楼南京阅江楼'
  //     }, {
  //       id: '0002',
  //       imgUrl: 'http://img1.qunarzz.com/sight/source/1505/e1/cdbf56d837da59.jpg_r_640x214_105fc3f2.jpg',
  //       title: '南京阅江楼',
  //       desc: '南京阅江楼南京阅江楼南京阅江楼南京阅江楼'
  //     }, {
  //       id: '0003',
  //       imgUrl: 'http://img1.qunarzz.com/sight/source/1509/31/534910d969850a.jpg_r_640x214_6ac50353.jpg',
  //       title: '南京阅江楼',
  //       desc: '南京阅江楼南京阅江楼南京阅江楼南京阅江楼'
  //     }]
  //   }
  // }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
   line-height: .8rem
   background: #eee
   text-indent: .2rem
 .item-img-wrapper
   overflow: hidden
   height: 0
   padding-bottom: 37.09%
   .item-img
     width: 100%
 .item-info
   padding: .1rem
   .item-title
     line-height: .54rem
     font-size: .32rem
     ellipsis()
   .item-desc
     line-height: .4rem
     color: #333
     ellipsis()
</style>
