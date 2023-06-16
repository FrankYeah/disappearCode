<template>
  <div class="map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="map-row0">
      <img class="map-img" src="@/assets/img/collect/chunchen.png" alt="fb">
      <nuxt-link to="/collect">
        <img class="map-img" src="@/assets/img/btn/backmap.png" alt="fb">
      </nuxt-link>
    </div>

    <div class="map-outer">
      <div class="map-left">
        <div class="map-box">
          <div class="map-row">
            <div>陳XX</div>
            <div class="map-want">想找</div>
            <div>美食</div>
          </div>
          <div class="map-text">捏糖人</div>
        </div>
      </div>
      <div class="map-right">

        <div class="map-box2">
          <div class="map-row2">
            <div>
              <div class="map-name">陳XX</div>
              <div class="map-row3">
                <div class="map-want2">想找</div>
                <div>美食</div>
              </div>
            </div>
            <div class="map-like">
              <div class="fb-like" data-href="https://frankyeah.github.io/disappear/anlei?id=陳秀美" data-width="300" data-layout="" data-action="" data-size="" data-share="true"></div>
            </div>
          </div>
          <div class="map-text2">小時候每次去中正公園都會買一支來吃現在都沒看到過這類的了，如果可以想讓小孩也吃吃看我們以前的零食現在頂多看到畫糖而不是吹糖捏糖，傳統的零食工藝也消失了</div>
          <div class="map-title">我提供的線索</div>
          <div class="map-text3">我只知道中正公園忠烈祠旁的公園有一位阿伯假日都會在那擺攤，有動物的模具就可以做吹糖也可以講想要什麼就用捏糖</div>
        </div>
        
        <div class="map-fb">
          <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/anlei?id=陳秀美" data-width="300" data-colorscheme="light" data-numposts="5"></div>
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
