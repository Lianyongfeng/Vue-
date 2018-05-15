<template>
  <div class="header">
    <div class="nav">
      <div class="icon-phone"></div>
      <img src="./logo.jpg" width="36" height="45" class="logo">
      <div class="icon-menu"></div>
    </div>
    <banner></banner>
    <traval></traval>
    <hotAddress></hotAddress>
    <topTraval></topTraval>
    <productExperience></productExperience>
    <PersonalTailor></PersonalTailor>
    <bottom></bottom>
  </div>
</template>

<script type="text/ecmascript-6">
import Banner from '@/components/Banner/Banner'
import traval from '@/components/traval/traval'
import hotAddress from '@/components/hotAddress/hotAddress'
import topTraval from '@/components/topTraval/topTraval'
import productExperience from '@/components/productExperience/productExperience'
import PersonalTailor from '@/components/PersonalTailor/PersonalTailor'
import bottom from '@/components/bottom/bottom'
export default {
  created () {
    this.$http.get('/api/changeImg')
      .then((response) => {
        response = response.body
        this.changeImg = response.data
      })
  },
  components: {
    Banner,
    traval,
    hotAddress,
    topTraval,
    productExperience,
    PersonalTailor,
    bottom
  }
}

</script>

<style lang="stylus" rel="stylesheet/stylus">
.header
  width: 100%
  .nav
    width: 100%
    height: 45px
    z-index: 200
    background: rgba(0,0,0,0.8)
    align-items: center
    display: flex
    justify-content: space-between
    .icon-phone
      font-size: 20px
      color: #fff
      margin-left: 1rem
    .icon-menu
      font-size: 20px
      color: #fff
      margin-right: 1rem
</style>
