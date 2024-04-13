<template>
  <div class="north">
    <div>
      <button @click="playSound">播放聲音</button>
      <audio ref="audioPlayer" src="plum.mp3"></audio>
      <img class="about-box-link" src="@/assets/img/social/link.png" alt="fb">
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
      // audioSrc: require('@/assets/plum.mp3')
    }
  },
  async mounted () {

  },
  destroyed () {
    
  },
  computed: {
    
  },
  methods: {
    playSound() {
      this.$refs.audioPlayer.play();
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.north {
  background: red;

}

@media( max-width: 1023px ){



}

</style>
