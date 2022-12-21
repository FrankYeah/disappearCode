<template>
  <div class="about"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
  <div class="about-box">
    <div class="about-box-text">
      怪奇團隊 – 關於我們<br><br>
      一盒桌遊、一次聚餐、一條皮帶，<br>
      一場還未止息的旅途。<br>
      在追尋著什麼呢？<br>
      也沒有吧！<br>
      就只是一群人，<br>
      用戲劇、用文字、用遊戲、用藝術，<br>
      貫徹著想為基隆做些什麼的心情。<br>
      這樣的一個團隊，<br>
      說來，還真是怪奇啊。
    </div>
    <div v-if="isShow" class="about-box-intro">
      <div class="about-box-intro-row">
        <img
          @click="imgBack"
          class="about-box-intro-left"
          src="@/assets/img/btn/left.png"
          alt="left"
        >
        <div class="about-box-intro-img"
          :style="[
            {'backgroundImage': 'url(' + total[currentNum].img + ')'}
          ]"
        ></div>

        <img
          @click="imgForward"
          class="about-box-intro-right"
          src="@/assets/img/btn/right.png"
          alt="left"
        >
      </div>

      <div class="about-box-intro-name">{{ total[currentNum].name }}</div>
      <div class="about-box-intro-text">{{ total[currentNum].text }}</div>
      <a :href='total[currentNum].link' target="_blank" class="about-box-intro-link-box">
        <img class="about-box-intro-link" src="@/assets/img/social/link.png" alt="fb">
      </a>
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
      currentData: {
        img: require('@/assets/img/group/11.png'),
        name: '無用學堂/鄭十一',
        text: '世上沒有什麼是真的無用',
        link: 'https://www.wu-yong.com/'
      },
      currentNum: 0,
      isShow: false,
      total: [
        {
          img: require('@/assets/img/group/11.png'),
          name: '無用學堂/鄭十一',
          text: '世上沒有什麼是真的無用',
          link: 'https://www.wu-yong.com/'
        },
        {
          img: require('@/assets/img/group/harmony.png'),
          name: '小哈',
          text: '在山裡海裡走跳、愛野生動物更勝於人類ㄉ人類',
          link: ''
        },
        {
          img: require('@/assets/img/group/tutu.png'),
          name: '阿普蛙/杜杜',
          text: '就是個杜杜。',
          link: 'https://www.facebook.com/Wasupstudio'
        },
        {
          img: require('@/assets/img/group/mei.png'),
          name: '阿普蛙/侃眉',
          text: '用生命影響生命，讓人看見只要「存在」就有價值。',
          link: 'https://www.facebook.com/Wasupstudio'
        },
        {
          img: require('@/assets/img/group/chihon.png'),
          name: '大可思創/奇鴻',
          text: 'chideart (chi+idea+art)',
          link: ''
        },
        {
          img: require('@/assets/img/group/pinwen.png'),
          name: '慾望劇團/品文',
          text: '用戲劇拉近人與人之間的距離',
          link: 'https://www.facebook.com/desiretroupe'
        },
        {
          img: require('@/assets/img/group/yiwei.png'),
          name: '西打藍/奕緯',
          text: '愛基隆、愛文字的西打',
          link: 'https://siddharam.com/'
        },
        {
          img: require('@/assets/img/group/chiyi.png'),
          name: '阿普蛙/無建議',
          text: '臭衣物口袋裡的發票，在翻滾的洗衣機中思考自己存在的意義。',
          link: 'https://www.facebook.com/Wasupstudio'
        },
      ]
    }
  },
  async mounted () {
    this.total.sort(() => Math.random() - 0.5)
    this.isShow = true
  },
  destroyed () {
    
  },
  computed: {
    
  },
  methods: {
    imgBack() {
      if(this.currentNum == 0) {
        this.currentNum = 7
      } else {
        this.currentNum--
      }
      
    },
    imgForward() {
      if(this.currentNum == 7) {
        this.currentNum = 0
      } else {
        this.currentNum++
      }
      
    },
    
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.about {
  width: 100vw;
  height: calc(100vh - 100px);
  display: flex;
  justify-content: center;
  padding-top: 100px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-box {
    display: flex;
    font-size: 24px;

    &-text {
      margin-top: 60px;
      width: 400px;
    }

    &-intro {

      &-row {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 600px;
      }

      &-left {
        width: 108px;
        height: 135px;
        cursor: pointer;
        opacity: 0.6;

        &:hover {
          opacity: 1;
        }
      }

      &-right {
        width: 108px;
        height: 135px;
        cursor: pointer;
        opacity: 0.6;

        &:hover {
          opacity: 1;
        }
      }

      &-img {
        width: 250px;
        height: 360px;
        background-repeat: no-repeat;
        background-size: contain;
        background-position-x: center;
        background-position-y: center;
      }

      &-name {
        text-align: center;
      }

      &-text {
        margin-top: 20px;
        text-align: center;
        line-height: 1.5;
      }

      &-link-box {
        margin-top: 20px;
        display: flex;
        justify-content: center;
      }

      &-link {
        
      }

    }
  }
}

</style>
