<template>
  <div class="collect"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <img class="collect-rwd-img" src="@/assets/img/base/keelung-map.png" alt="map">
    <div class="collect-map"
      :style="{
        
      }"
    >
      <!-- <nuxt-link to="/map-zenai" class="collect-box collect-box-1">
        <img class="collect-img" src="@/assets/img/collect/qinai.png" alt="btn">2
      </nuxt-link>
      <nuxt-link to="/map-anlei" class="collect-box collect-box-2">
        <img class="collect-img collect-img-special" src="@/assets/img/collect/anlei.png" alt="btn">1
      </nuxt-link>
      <nuxt-link to="/map-sinyi" class="collect-box collect-box-3">
        <img class="collect-img" src="@/assets/img/collect/sinyi.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/map-chunchen" class="collect-box collect-box-4">
        <img class="collect-img" src="@/assets/img/collect/chunchen.png" alt="btn">1
      </nuxt-link>
      <nuxt-link to="/map-chunshan" class="collect-box collect-box-5">
        <img class="collect-img" src="@/assets/img/collect/chunshan.png" alt="btn">1
      </nuxt-link>
      <nuxt-link to="/map-qidu" class="collect-box collect-box-6">
        <img class="collect-img collect-img-special" src="@/assets/img/collect/qidu.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/map-nunnun" class="collect-box collect-box-7">
        <img class="collect-img" src="@/assets/img/collect/nunnun.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="map-none" class="collect-box collect-box-8">
        <img class="collect-img" src="@/assets/img/collect/none.png" alt="btn">0
      </nuxt-link> -->

      <nuxt-link to="/map-zenai" class="collect-box collect-box-1">
        <img class="collect-img" src="@/assets/img/collect/qinai.png" alt="btn">1
      </nuxt-link>
      <nuxt-link to="/collect" class="collect-box collect-box-2">
        <img class="collect-img collect-img-special" src="@/assets/img/collect/anlei.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/collect" class="collect-box collect-box-3">
        <img class="collect-img" src="@/assets/img/collect/sinyi.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/collect" class="collect-box collect-box-4">
        <img class="collect-img" src="@/assets/img/collect/chunchen.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/map-chunshan" class="collect-box collect-box-5">
        <img class="collect-img" src="@/assets/img/collect/chunshan.png" alt="btn">1
      </nuxt-link>
      <nuxt-link to="/collect" class="collect-box collect-box-6">
        <img class="collect-img collect-img-special" src="@/assets/img/collect/qidu.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="/collect" class="collect-box collect-box-7">
        <img class="collect-img" src="@/assets/img/collect/nunnun.png" alt="btn">0
      </nuxt-link>
      <nuxt-link to="collect" class="collect-box collect-box-8">
        <img class="collect-img" src="@/assets/img/collect/none.png" alt="btn">0
      </nuxt-link>

    </div>

    <nuxt-link to="/secret" class="collect-link">
      <img class="collect-link-img" src="@/assets/img/index/project-case.png" alt="btn">
    </nuxt-link>

  </div>
</template>

<script>


export default {
  layout: 'default',
  components: {

  },
  props: {

  },
  data () {
    return {
      isFromIndexPage: false
    }
  },
  beforeRouteEnter(to, from, next) {
      next(vm => {
      // 判斷是否從首頁過來
      if(from.name) {
      console.log(from.name.substr(0, 5))
        if(from.name.substr(0, 8) == 'index') {
          console.log(from.name.substr(0, 8))
          console.log(from.name)
          vm.isFromIndexPage = true
        }
      }
      vm.prevRoute = from
    })
  },
  async mounted () {
    if(this.isFromIndexPage) {
      location.reload()
    }
  },
  destroyed () {
    
  },
  computed: {
    
  },
  methods: {
    
    
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.collect {
  position: relative;
  width: 100vw;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  color: white;

  &-rwd-img {
    display: none;
  }

  &-map {
    position: relative;
    width: 800px;
    height: 580px;
    margin: 81px 0px 20px;
    align-items: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;
    background-image: url('../assets/img/base/keelung-map.png');
  }

  &-box {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &-img {
    width: 120px;
    height: 60px;
  }

  &-box-1 {
    top: 250px;
    left: 450px;
  }

  &-box-2 {
    top: 200px;
    left: 340px;
  }

  &-box-3 {
    top: 200px;
    right: 100px;
  }

  &-box-4 {
    top: 100px;
    right: 100px;
  }

  &-box-5 {
    top: 70px;
    left: 380px;
  }

  &-box-6 {
    top: 300px;
    left: 200px;
  }

  &-box-7 {
    top: 400px;
    left: 450px;
  }

  &-box-8 {
    bottom: 50px;
  }

  &-link {
    position: absolute;
    top: 80px;
    left: 40px;
    z-index: 2;

    &-img {
      
    }
  }
  
}

@media( max-width: 1023px ){

.collect {
  
  &-rwd-img {
    display: block;
    max-width: 500px;
    width: calc(100% - 40px);
    margin: 80px 20px 0px;
  }

  &-map {
    width: 320px;
    height: 100%;
    margin: 20px 0px 0px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    background-image: none;
  }

  &-box {
    position: initial;
  }

  &-img {
    width: 100px;
    height: 50px;
  }

  &-img-special {
    width: 98px;
    height: 48px;
    padding-top: 6px;
  }

  &-box-1 {
    
  }

  &-box-2 {
    
  }

  &-box-3 {
    
  }

  &-box-4 {
    
  }

  &-box-5 {
    
  }

  &-box-6 {
    
  }

  &-box-7 {
    
  }

  &-box-8 {

  }

  &-link {
    top: 60px;
    left: 50%;
    transform: translate(-50%, -0%);

    &-img {
      width: 120px;
    }
  }
}

}

</style>
