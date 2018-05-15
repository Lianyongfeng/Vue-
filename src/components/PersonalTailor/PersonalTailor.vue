<template>
  <div class="PersonalTailor-wrpper">
    <h2 class="h2">私人定制</h2>
    <div class="input-wrapper">
      <div v-for="(item,index) in PersonalTailor" :key="index" class="input-box">
        {{ item.private.span }}
        <input type="text" :placeholder="item.private.text" name="text"/>
      </div>
      <button>现在提交</button>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
export default {
  data () {
    return {
      PersonalTailor: []
    }
  },
  created () {
    this.$http.get('/api/PersonalTailor')
      .then((response) => {
        response = response.body
        this.PersonalTailor = response.data
      })
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.PersonalTailor-wrpper
  width: 100%
  background: white
  overflow: hidden
  margin-top: 1rem
  height: 415px
  .h2
    text-align: center
    font-weight: 100
    margin-top: 3rem
  .input-wrapper
    display: flex
    justify-content: center
    flex-wrap: wrap
    .input-box
      width: 41%
      border: 1px #999 solid
      height: 44px
      border-radius: 4px
      display: flex
      justify-content: center
      align-items: center
      color: black
      font-size: 12px
      font-weight: bold
      margin: 8px
      input
        background-color: white
        width: 70%
        height: 32px
        border: none
        margin-left: 6px
    button
      width: 172px
      height: 43px
      font-size: 16px
      border-radius: 4px
      background-color: #0853B9
      color: #FFFFFF
      font-weight: bold
      line-height: 43px
      padding: 0px 0px
      text-align: center
      border: 1px #fff solid
      margin-top: 30px
</style>
