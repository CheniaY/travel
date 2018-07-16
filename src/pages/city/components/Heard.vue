<template>
  <div class="heard">
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
     国内城市
  </div>
</template>
<script>
export default {
  name: 'CityHeard'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .heard
    position: relative
    height: $headerHeight
    line-height: $headerHeight
    background: $bgColor
    text-align: center
    color: #fff
    font-size: .4rem
    overflow: hidden
    .header-back
      position: absolute
      left: 0
      font-size: .4rem
      color: #fff
</style>
