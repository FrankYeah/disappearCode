<template>
  <div class="collect"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
  <div class="collect-map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/base/keelung-map.png') + ')'
    }"
  >
    <nuxt-link to="/map-anlei" class="collect-box collect-box-1">
      <img class="collect-img" src="@/assets/img/collect/qinai.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-2">
      <img class="collect-img" src="@/assets/img/collect/anlei.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-3">
      <img class="collect-img" src="@/assets/img/collect/sinyi.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-4">
      <img class="collect-img" src="@/assets/img/collect/chunchen.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-5">
      <img class="collect-img" src="@/assets/img/collect/chunshan.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-6">
      <img class="collect-img" src="@/assets/img/collect/qidu.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-7">
      <img class="collect-img" src="@/assets/img/collect/nunnun.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-7">
      <img class="collect-img" src="@/assets/img/collect/nunnun.png" alt="btn">
    </nuxt-link>
    <nuxt-link to="/map-anlei" class="collect-box collect-box-8">
      <img class="collect-img" src="@/assets/img/collect/none.png" alt="btn">
    </nuxt-link>

  </div>
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
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  color: white;

  &-map {
    position: relative;
    width: 800px;
    height: 580px;
    align-items: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-position-x: center;
    background-position-y: center;
  }

  &-box {
    position: absolute;
  }

  &-img {
    width: 120px;
    height: 60px;
    cursor: pointer;
    opacity: 0.6;

    &:hover {
      opacity: 1;
    }
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
}

@media( max-width: 1023px ){



}

</style>
