<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  // props: {
  //   list: Array
  // },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      list: [{
        id: '0001',
        imgUrl: 'https://images3.c-ctrip.com/hotel/2018/05/byy_780_235.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://images3.c-ctrip.com/ad/bigbutton/promotion/201806/0605_sjb_780_235.jpg'
      }, {
        id: '0003',
        imgUrl: 'https://images3.c-ctrip.com/ad/bigbutton/promotion/201806/0626_sxkh_780_235.jpg'
      }

      ]
    }
  }
  // computed: {
  //   showSwiper () {
  //     return this.list.length
  //   }
  // }
}
</script>

<style lang="stylus" scoped>
  //样式进行穿透，只要wrapper下出现swiper那个属性，就使用该样式，而不受scoped的限制
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.25%
    background: #eee
    .swiper-img
      width: 100%
</style>
