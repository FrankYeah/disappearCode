<template>
  <div class="index">
    <!-- 第一 run -->
    <div v-if="step == 0"
      @click="step = 1"
      class="index-outer"
    >
      <div class="index-bg1"
        :style="{
          'backgroundImage' : 'url(' + require('@/assets/img/index/bg1.png') + ')'
        }"
      ></div>
    </div>

    <!-- 第二 run -->
    <div v-else-if="step == 1"
      @click="step = 2"
      class="index-outer"
    >
      <div class="index-float-text">童年的消失</div>
      <div class="index-bg2"
        :style="{
          'backgroundImage' : 'url(' + require('@/assets/img/index/solo.png') + ')'
        }"
      ></div>
    </div>

    <!-- 第三 run -->
    <div v-if="step == 2" class="index-outer">
      <div class="index-bg1"
        :style="{
          'backgroundImage' : 'url(' + require('@/assets/img/index/bg2.png') + ')'
        }"
      ></div>
      <div class="index-box">
            <img class="index-lightbox" src="@/assets/img/index/brand.gif" alt="btn">
        <div class="index-row">
          <nuxt-link to="/undergoing" class="index-">
            <img class="index-btn" src="@/assets/img/index/undergoing.png" alt="btn">
          </nuxt-link>
          <nuxt-link to="/collect" class="index-">
            <img class="index-btn" src="@/assets/img/index/collect.png" alt="btn">
          </nuxt-link>
        </div>
      </div>
      <nuxt-link to="/secret" class="index-secret">
        <img class="index-secret" src="@/assets/img/index/secret.png" alt="btn">
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
      step: 0
    }
  },
  async mounted () {

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

.index {
 
 &-outer {
   position: relative;
   height: 100vh;
 }

 &-bg1 {
  position: absolute;
  padding-top: 80px;
  width: 100%;
  height: calc(100% - 80px);
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
 }

 &-bg2 {
  position: absolute;
  right: 270px;
  bottom: 50px;
  width: 140px;
  height: 470px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
 }

 &-float-text {
  position: absolute;
  right: 270px;
  top: 120px;
  font-size: 40px;
  color: black;
 }

 &-box {
  position: absolute;
  top: 140px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
 }

 &-lightbox {
   width: 500px;
 }

 &-row {
   
 }

 &-btn {
   
 }

 &-secret {
   position: absolute;
   right: 50px;
   top: 40%;
 }

}

</style>
