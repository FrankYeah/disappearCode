<template>
  <div class="map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="map-row0">
      <img class="map-img" src="@/assets/img/collect/chunshan.png" alt="fb">
      <nuxt-link to="/collect">
        <img class="map-img" src="@/assets/img/btn/backmap.png" alt="fb">
      </nuxt-link>
    </div>

    <div class="map-outer">
      <div class="map-left">
        <div class="map-box">
          <div class="map-row">
            <div>吳XX</div>
            <div class="map-want">想找</div>
            <div>建築/場所</div>
          </div>
          <div class="map-text">章魚游泳池</div>
        </div>
      </div>
      <div class="map-right">

        <div class="map-box2">
          <div class="map-row2">
            <div>
              <div class="map-name">吳XX</div>
              <div class="map-row3">
                <div class="map-want2">想找</div>
                <div>建築/場所</div>
              </div>
            </div>
            <div class="map-like">
              <div class="fb-like" data-href="https://frankyeah.github.io/disappear/anlei?id=吳芷儀" data-width="300" data-layout="" data-action="" data-size="" data-share="true"></div>
            </div>
          </div>
          <div class="map-text2">以前章魚游泳池也是很適合全家一起游泳的場所，孩子可以玩水、附近也有許多熱鬧的攤家、也有完善的設施，但現在只剩下海興以及沙灘，有點太過開放的場域，對於大家要鄰近海邊玩水的感覺比較困難～～</div>
          <div class="map-title">我提供的線索</div>
          <div class="map-text3">在大約國小前，應該80年？有個很大的章魚造景，記得好像還有滑水道？池子很大，大人小孩都能一起玩，也很乾淨！</div>
        </div>
        
        <div class="map-fb">
          <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/anlei?id=吳芷儀" data-width="300" data-colorscheme="light" data-numposts="5"></div>
        </div>
      </div>
    </div>

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
