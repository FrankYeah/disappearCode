<template>
  <div class="map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="map-row0">
      <img class="map-img" src="@/assets/img/collect/qidu.png" alt="fb">
      <nuxt-link to="/collect">
        <img class="map-img" src="@/assets/img/btn/backmap.png" alt="fb">
      </nuxt-link>
    </div>

    <!-- <div class="map-outer">
      <div class="map-left">
        <div class="map-box">
          <div class="map-row">
            <div>邵XX</div>
            <div class="map-want">想找</div>
            <div>美食</div>
          </div>
          <div class="map-text">以前有個三輪車阿伯會賣肉圓跟四神湯</div>
        </div>
      </div>
      <div class="map-right">

        <div class="map-box2">
          <div class="map-row2">
            <div>
              <div class="map-name">邵XX</div>
              <div class="map-row3">
                <div class="map-want2">想找</div>
                <div>美食</div>
              </div>
            </div>
            <div class="map-like">
              <div class="fb-like" data-href="https://frankyeah.github.io/disappear/anlei?id=邵小姐" data-width="300" data-layout="" data-action="" data-size="" data-share="true"></div>
            </div>
          </div>
          <div class="map-text2">小學阿公放學接我們回家時，都會遇到三輪車阿伯，剛好賣到我們家樓下，阿公會買一顆肉圓一起吃，有時候也會買四神湯，阿伯的四神湯味道很奇妙，跟現在市面上的都不一樣，非常令人懷念</div>
          <div class="map-title">我提供的線索</div>
          <div class="map-text3">記得阿伯的三輪車都是大概小學放學時間到崇德路賣的，只有賣肉圓跟四神湯</div>
        </div>
        
        <div class="map-fb">
          <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/anlei?id=邵小姐" data-width="300" data-colorscheme="light" data-numposts="5"></div>
        </div>
      </div>
    </div> -->

    <!-- <div class="fb-comments map-fb" data-href="https://siddharam.com/anlei" data-width="300" data-colorscheme="light" data-numposts="5"></div> -->


</div>
</template>

<script>

import Vue from 'vue'

export default {
  layout: 'default',
  components: {

  },
  props: {

  },
  data () {
    return {
      isFBReady: false,
      isFromIndexPage: false
    }
  },
    beforeRouteEnter(to, from, next) {
      next(vm => {
      // 判斷是否從首頁過來
      if(from.name) {
      console.log(from.name.substr(0, 5))
        if(from.name.substr(0, 8) == 'collect') {
          console.log(from.name.substr(0, 8))
          console.log(from.name)
          vm.isFromIndexPage = true
        }
      }
      vm.prevRoute = from
    })
  },
  mounted () {
    if(this.isFromIndexPage) {
      location.reload()
    }
    // this.isFBReady = Vue.FB != undefined
    // window.addEventListener('fb-sdk-ready', this.onFBReady)
  },
  beforeDestroy: function () {
    // window.removeEventListener('fb-sdk-ready', this.onFBReady)
  },
  methods: {
    onFBReady: function () {
      // this.isFBReady = true
    }
  },
  watch: {
    
  }
}
</script>


<style lang="scss" scoped>



</style>
