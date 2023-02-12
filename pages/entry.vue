<template>
  <div class="index">
    <!-- 第三 run -->
    <div class="index-outer">
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
            <img class="index-btn" src="@/assets/img/index/total-case.png" alt="btn">
          </nuxt-link>
          <nuxt-link to="/secret" class="index-">
            <img class="index-btn" src="@/assets/img/index/project-case.png" alt="btn">
          </nuxt-link>
        </div>
      </div>
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
  top: 190px;
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
  cursor: pointer;
  opacity: 0.6;

  &:hover {
    opacity: 1;
  }
   
 }

 &-secret {
   position: absolute;
   right: 50px;
   top: 40%;
 }

}

</style>
