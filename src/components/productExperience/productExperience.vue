<template>
  <div class="productExperience-wrapper">
    <h2 class="h2">4S产品体验</h2>
    <div class="logo-wrapper">
      <div class="img-conent" v-bind:style="{ 'background-image': 'url(' + item.experience.img + ')','background-repeat':'no-repeat' }" v-for="(item,index) in productExperience" :key="index">
        <h1 class="title">{{ item.experience.name }}</h1>
        <h2 class="title-two">{{ item.experience.span }}</h2>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data () {
    return {
      productExperience: []
    }
  },
  created () {
    this.$http.get('/api/productExperience')
      .then((response) => {
        response = response.body
        this.productExperience = response.data
      })
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.productExperience-wrapper
  width: 100%
  background: white
  overflow: hidden
  margin-top: 1rem
  height: 415px
  .h2
    text-align: center
    font-weight: 100
    margin-top: 1rem
  .logo-wrapper
    width: 100%
    display: flex
    justify-content: center
    flex-wrap: wrap
    .img-conent
      width: 45%
      height: 154px
      background: #f4f4f4
      background-position: center top
      margin: 8px
      .title
        text-align: center
        font-size: 16px
        font-weight: bold
        color: #333333
        margin-top: 90px
      .title-two
        text-align: center
        font-size: 14px
        font-weight: normal
        color: #666666
</style>
