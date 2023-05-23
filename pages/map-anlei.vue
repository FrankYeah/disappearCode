<template>
  <div class="map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="map-box">
      <div class="map-left">
        <img class="map-img" src="@/assets/img/collect/anlei.png" alt="btn">
        
        <nuxt-link to="/collect" class="">
          <img class="map-back" src="@/assets/img/btn/backmap.png" alt="btn">
        </nuxt-link>
      </div>
      <div class="map-right">
        <div></div>
        <div class="fb-comments map-fb" data-href="https://siddharam.com/anlei" data-width="300" data-colorscheme="light" data-numposts="5"></div>
      </div>

    </div>

  <div>
    
  </div>

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
