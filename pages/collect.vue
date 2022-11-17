<template>
  <div class="collect"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/qinai.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/anlei.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/sinyi.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/chunchen.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/chunshan.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/qidu.png" alt="btn">
    <div></div>
  </div>
  <div class="collect-box">
    <img class="collect-img" src="@/assets/img/collect/nunnun.png" alt="btn">
    <div></div>
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

.collect {
  width: 100vw;
  height: calc(100%);
  display: flex;
  padding: 120px 0px 40px;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-box {
    display: flex;
    width: 80%;
    font-size: 24px;
  }
}

</style>
