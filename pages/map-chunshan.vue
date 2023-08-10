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

    <div class="map-box">
      <a class="map-item"
        v-for="(item, index) in items"
        :key="index"
        :href="item.link"
        target="_blank"
      >
        <div class="map-text1">{{ item.name }} 想找 {{ item.class }}</div>
        <div class="map-text2">{{ item.text }}</div>
      </a>
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
      items: [
        { name: '吳小姐', class: '場所', text: '章魚游泳池', link: 'https://www.facebook.com/100088446610563/posts/pfbid0362nhTnJMLERWLfVTVUBAAzCg42trcp79vBBoni2gpk7PpYTVWfv5CMceJ4dFtiFhl/?mibextid=cr9u03' },
        // { name: '', class: '', text: '', link: '' },
      ]
    }
  },
  mounted () {
    
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
