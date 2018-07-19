<template>
<div>
  <div class="banner" @click='handleBannerClick'>
    <img class="banner-img" :src="bannerImage">
    <div class="banner-info">
      <div class="banner-title">
        {{this.sightName}}
      </div>
      <div class="banner-number">
        <span class="iconfont banner-icon">&#xe63f;</span>
        {{this.imageNumber}}
      </div>
    </div>
  </div>
 <fade-animation>
   <common-gallary
     :galleryImage = 'galleryImage'
     v-show='showGallary'
     @close='handleBannerClick'
   >
   </common-gallary>
 </fade-animation>
</div>
</template>
<script>
import CommonGallary from 'common/gallary/gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    bannerImage: String,
    sightName: String,
    galleryImage: Array
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  data () {
    return {
      showGallary: false
    }
  },
  computed: {
    imageNumber () {
      return this.galleryImage.length
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = !this.showGallary
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      left: 0
      right: 0
      bottom: 0
      font-size: .32rem
      color: #fff
      height: .6rem
      line-height: .6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        float: left
        padding-left: .2rem
      .banner-number
        float:right
        height: .4rem
        line-height: .4rem
        margin-top: .1rem
        padding: 0 .4rem
        background: rgba(0, 0, 0, 0.4)
        border-radius: .2rem
</style>
