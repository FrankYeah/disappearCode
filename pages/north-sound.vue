<template>
  <div class="north">
    <div class="north-box">
      <!-- <img @click="playSound1" class="north-music north-music1" src="@/assets/img/music/smallruo.jpeg" alt="music"> -->
      <img @click="playSound1" class="north-music north-music1" src="@/assets/img/music/smallruo1.webp" alt="music">
      <div  class="north-text">小鑼</div>

      <img @click="playSound2" class="north-music north-music2" src="@/assets/img/music/sona1.webp" alt="music">
      <!-- <img @click="playSound2" class="north-music north-music2" src="@/assets/img/music/sona.png" alt="music"> -->
      <div  class="north-text">嗩吶</div>

      <!-- <img @click="playSound3" class="north-music north-music3" src="@/assets/img/music/tamdrum.png" alt="music"> -->
      <img @click="playSound3" class="north-music north-music2" src="@/assets/img/music/tamdrum1.webp" alt="music">
      <div  class="north-text">堂鼓</div>

      <!-- <img @click="playSound4" class="north-music north-music4" src="@/assets/img/music/yehu.png" alt="music"> -->
      <img @click="playSound4" class="north-music north-music2" src="@/assets/img/music/yehu2.webp" alt="music">
      <div  class="north-text">椰胡</div>

      <audio ref="audioPlayer1" src="smallruo.m4a"></audio>
      <audio ref="audioPlayer2" src="sona.m4a"></audio>
      <audio ref="audioPlayer3" src="tamdrum.m4a"></audio>
      <audio ref="audioPlayer4" src="yehu.m4a"></audio>
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
    },
    playSound4() {
      this.$refs.audioPlayer4.play();
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.north {

  &-box {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
  }

  &-music {
    width: 200px;
    cursor: pointer;

    &:hover {
      opacity: 0.4;
    }
  }
  
  &-music1 {

    &:hover {
      transition: 0.3s;
    }
  }
  
  &-music2 {

    &:hover {
      transition: 0.3s;
    }
  }
  
  &-music3 {

    &:hover {

      transition: 0.3s;
    }
  }
  
  &-music4 {

    &:hover {
      transition: 0.3s;
    }
  }

  &-text {
    color: black;
  }

}

@media( max-width: 1023px ){



}

</style>
