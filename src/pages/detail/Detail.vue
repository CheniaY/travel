<template>
  <div>
    <detail-banner
      :bannerImage = 'bannerImg'
      :galleryImage = 'gallaryImgs'
      :sightName = 'sightName'
    ></detail-banner>
    <detail-header></detail-header>
      <div class="content">
      <detail-list
        :list = 'list'
      ></detail-list>
    </div>
  </div>
</template>
<script>
import DetailBanner from './components/Banner'
import DetailList from './components/List'
import DetailHeader from './components/Header'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailHeader,
    DetailBanner,
    DetailList
  },
  data () {
    return {
      bannerImg: '',
      sightName: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSuc)
    },
    getDetailInfoSuc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.sightName = data.sightName
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem

</style>
