<template>
  <div class="about"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
  <div class="about-box">
    <div class="about-box-text">
      <div class="about-box-head">消失事務所</div>
      歡迎來到消失事務所，這是「雞籠怪奇」團隊最近想玩的主題，想邀請基隆人們跟我們一起玩。不論是過去的一段記憶、體驗，或是物品，都可以來信告知您的需求，我們會在評估後，結合團隊及大眾的力量，協助您找回消失的事物（但不保證事務所自身何時消失唷）。<br><br>
      
      <nuxt-link to="/north-sound">
      <div class="about-box-head">怪奇團隊</div>
      </nuxt-link>
      由雞籠在地團隊組成，包含：文安社區 X 慾望劇團 X 阿普蛙工作室 X 無用學堂 X 西打藍 X 小哈。以一場飯局為契機，加上一點想在雞籠做些什麼的動力，最終形成了現在有著多元組成的怪奇團隊。<br><br>
      
      <div class="about-box-head">過去案例</div>
      <a href='https://frankyeah.github.io/klkuaiki/index.html' target="_blank" class="about-box-link-box">
        2020：怪奇事件簿、咱的聲音
        <img class="about-box-link" src="@/assets/img/social/link.png" alt="fb">
      </a>
      <a href='https://frankyeah.github.io/klkuaikii/' target="_blank" class="about-box-link-box">
        2021：怪奇逃走中-混血探員
        <img class="about-box-link" src="@/assets/img/social/link.png" alt="fb">
      </a>
      
      <a href='https://www.facebook.com/klkuaiki' target="_blank" class="about-box-link-box">
        粉專連結
        <img class="about-box-link" src="@/assets/img/social/link.png" alt="fb">
      </a>
    </div>
    <div v-if="isShow" class="about-box-intro">
      <div class="about-box-intro-row">
        <img
          @click="imgBack"
          class="about-box-intro-left"
          src="@/assets/img/btn/left.png"
          alt="left"
        >
        <div :class="['about-box-intro-img',
          {'about-box-intro-img-big': currentNum ==  0},
          {'about-box-intro-img-big': currentNum ==  7},
        ]"
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
      <div class="about-box-intro-text" v-html="total[currentNum].text"></div>
      <a v-if="total[currentNum].link" :href='total[currentNum].link' target="_blank" class="about-box-intro-link-box">
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
      currentNum: 0,
      isShow: false,
      total: [
        {
          img: require('@/assets/img/group/11.png'),
          name: '無用學堂/鄭十一',
          text: '世上沒有什麼是真的無用<br>',
          link: 'https://www.wu-yong.com/'
        },
        {
          img: require('@/assets/img/group/harmony.png'),
          name: '小哈',
          text: '在山裡海裡走跳、愛野生動物更勝於人類ㄉ人類',
          link: 'https://www.facebook.com/klkuaiki'
        },
        {
          img: require('@/assets/img/group/tutu.png'),
          name: '阿普蛙/杜杜',
          text: '就是個杜杜。<br>',
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
          text: 'chideart (chi+idea+art)<br>',
          link: 'https://www.facebook.com/profile.php?id=100064638415232'
        },
        {
          img: require('@/assets/img/group/pinwen.png'),
          name: '慾望劇團/品文',
          text: '用戲劇拉近人與人之間的距離<br>',
          link: 'https://www.facebook.com/desiretroupe'
        },
        {
          img: require('@/assets/img/group/yiwei.png'),
          name: '西打藍/奕緯',
          text: '愛基隆、愛文字的西打<br>',
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
    this.currentNum = Math.floor(Math.random() * (this.total.length - 1))
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
  min-height: calc(100vh - 100px);
  padding-bottom: 40px;
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

    &-head {
      font-size: 24px;
      margin-bottom: 10px;
      width: 400px;
    }

    &-text {
      margin-top: 60px;
      width: 400px;
      font-size: 18px;
    }

    &-link-box {
      margin-top: 10px;
      display: flex;
      align-items: center;
      opacity: 0.7;
    }

    &-link {
      width: 18px;
      height: 18px;
      margin-left: 8px;
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
        width: 410px;
        height: 50px;
        margin: 20px auto 0px;
        padding: 0px 20px;
        font-size: 18px;
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

@media( max-width: 1023px ){

.about {

  &-box {
    flex-direction: column;
    font-size: 20px;

    &-head {
      width: 100%;
      font-size: 20px;
    }

    &-text {
      margin: 10px 15px;
      width: calc(100% - 30px);
      font-size: 16px;
    }

    &-link-box {
      
    }

    &-link {
      width: 14px;
      height: 14px;
    }

    &-intro {
      margin-top: 10px;

      &-row {
        width: 100%;
        height: 220px;
        margin: auto;
      }

      &-left {
        width: 70px;
        height: 90px;
      }

      &-right {
        width: 70px;
        height: 90px;
      }

      &-img {
        width: 100px;
        height: 200px;
        margin: 0px 10px;
      }

      &-img-big {
        width: 120px;
        height: 240px;
        margin: 0px;
      }

      &-name {
        
      }

      &-text {
        width: auto;
        height: 62px;
        margin: 12px auto 0px;
        padding: 0px 20px;
        font-size: 16px;
      }

      &-link-box {
        margin-top: 0px;
      }

      &-link {
        
      }

    }
  }
}

}

</style>
