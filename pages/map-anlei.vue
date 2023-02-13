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

.map {
  width: 100vw;
  min-height: calc(100vh - 120px);
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding-top: 120px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-box {
    display: flex;
    justify-content: space-between;
    width: 80%;
    margin: auto;
  }

  &-left {
    display: flex;
    flex-direction: column;
  }

  &-img {
    cursor: pointer;
    opacity: 0.6;

    &:hover {
      opacity: 1;
    }
  }

  &-back {
    width: 180px;
    height: 90px;
    margin-top: 300px;
    cursor: pointer;
    opacity: 0.6;

    &:hover {
      opacity: 1;
    }
  }

  &-right {
    width: 500px;
    min-height: 500px;
    background-color: aquamarine;
  }

  &-fb {
    
  }
}

@media( max-width: 1023px ){

.map {

  &-box {
    width: 95%;
    padding-bottom: 30px;
    flex-direction: column;
  }

  &-left {
    flex-direction: row;
  }

  &-img {
    width: 150px;
  }

  &-back {
    width: 150px;
    height: 75px;
    margin-top: 0px;
  }

  &-right {
    max-width: 500px;
    width: 100%;
    margin: auto;
  }

  &-fb {
    
  }
}

}

</style>
