<template>
  <div class="hotAddress-wrapper">
    <div class="title">
      <h2>热门目的地</h2>
      <a href="###">MORE ></a>
    </div>
    <div class="hotAddress-img-wrapper">
      <div class="content" v-for="(item,index) in hotAddress" :key="index">
        <img :src="item.hot.img" width="108" height="106"/>
        <h3>{{ item.hot.title }}</h3>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data () {
    return {
      hotAddress: []
    }
  },
  created () {
    this.$http.get('/api/hotAddress')
      .then((response) => {
        response = response.body
        this.hotAddress = response.data
      })
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.hotAddress-wrapper
  width: 100%
  background: white
  overflow: hidden
  margin-top: 1rem
  .title
    width: 100%
    display: flex
    h2
      font-weight: 100
      flex: 2
      text-align: right
      align-self: center
    a
      flex: 1
      text-decoration: none
      font-size: 12px
      text-align: center
      align-self: center
  .hotAddress-img-wrapper
    width: 100%
    display: flex
    justify-content: space-around
    flex-wrap: wrap
    .content
      height: 140px
      h3
        font-size: 14px
        font-weight: normal
        text-align: center
        line-height: 0
</style>
