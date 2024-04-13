<template>
  <div class="north">
    <div>
      <img @click="playSound1" class="north-music" src="@/assets/img/music/ba.jpeg" alt="music">
      <img @click="playSound2" class="north-music" src="@/assets/img/music/drum.jpeg" alt="music">
      <img @click="playSound3" class="north-music" src="@/assets/img/music/wiu.jpeg" alt="music">
      <audio ref="audioPlayer1" src="plum.mp3"></audio>
      <audio ref="audioPlayer2" src="punk.wav"></audio>
      <audio ref="audioPlayer3" src="small.wav"></audio>
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
    playSound1() {
      this.$refs.audioPlayer1.play();
    },
    playSound2() {
      this.$refs.audioPlayer2.play();
    },
    playSound3() {
      this.$refs.audioPlayer3.play();
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.north {
  

}

@media( max-width: 1023px ){



}

</style>
