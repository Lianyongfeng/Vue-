<template>
  <div class="topTraval">
    <h2>顶级度假</h2>
    <div class="img-wapper">
      <div class="img-conent" v-bind:style="{ 'background-image': 'url(' + item.traval.img + ')','background-repeat':'no-repeat' }" v-for="(item,index) in topTraval" :key="index">
        <div class="text-wapper">
          <a href="###">{{ item.traval.title }}</a>
          <p>{{ item.traval.span }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data () {
    return {
      topTraval: []
    }
  },
  created () {
    this.$http.get('/api/topTraval')
      .then((response) => {
        response = response.body
        this.topTraval = response.data
      })
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.topTraval
  width: 100%
  background: white
  overflow: hidden
  margin-top: 1rem
  h2
    text-align: center
    font-weight: 100
    margin-top: 1rem
  .img-wapper
    width: 100%
    .img-conent
      width: 100%
      height: 218px
      background-size: 100% 100%
      .text-wapper
        background: rgba(0,0,0,0.3)
        height: 100%
        text-align: center
        display: flex
        flex-wrap: wrap
        a
          width: 100%
          color: white
          text-decoration: none
          font-size: 20px
          font-weight: bold
          align-self: center
          margin-top: 70px
        p
          color: white
          width: 100%
          margin-bottom: 60px
          height: 1em
          line-height: 1em
</style>
