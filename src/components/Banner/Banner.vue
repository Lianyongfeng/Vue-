<template>
  <div class="swiper-container">
    <div class="swiper-wrapper">
      <div class="swiper-slide">
        <img src="http://m.dearisland.com/upload/2018031611185810332.jpg" height="218"/>
      </div>
      <div class="swiper-slide">
        <img src="http://m.dearisland.com/upload/2018031611174028196.jpg" height="218"/>
      </div>
      <div class="swiper-slide">
        <img src="http://m.dearisland.com/upload/2018031611182027416.jpg" height="218"/>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
</template>

<script type="text/ecmascript-6">
import Swiper from 'swiper'
import 'swiper/dist/css/swiper.min.css'
export default {
  data () {
    return {
      changeImg: []
    }
  },
  mounted () {
    var swiper = new Swiper('.swiper-container', {
      loop: true,
      speed: 600,
      autoplay: {
        delay: 2000,
        stopOnLastSlide: false,
        disableOnInteraction: false
      },
      pagination: {
        el: 'swiper-pagination'
      },
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev'
      },
      onTouchEnd: function () {
        swiper.startAutoplay()
      }
    })
  }
}
</script>

<style lang="stylus" rel="stylesheet/stylus">
.swiper-container
  width: 100%
  height: 220px
  .swiper-wrapper
    width: 100%
    height: 100%
  .swiper-slide
    background-position: center
    background-size: cover
    width: 100%
    height: 100%
    img
      width: 100%
      position: absolute
  .swiper-pagination-bullet
    width:0.833rem
    height: 0.833rem
    display: inline-block
    background: #7c5e53
</style>
