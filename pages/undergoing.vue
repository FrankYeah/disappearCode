<template>
  <div class="under"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
  <div class="under-box">
  
  
  誠徵老照片與老故事！<br><br>

  大家小時候有去過十八羅漢洞嗎🤔<br><br>

  基隆人小時候必去探險或是校外教學的地方！聽說裡面有很多神秘雕像跟民間傳說故事～好好奇哦！<br><br>

  網路上的資料很有限，除了之前很多網友分享的文章以外，不曉得大家有沒有自己曾經去過的老照片、或是有趣的故事可以分享呢？<br><br>

  雞籠怪奇團隊現在正在挖掘十八羅漢洞的故事～想跟大家徵求十八羅漢洞的經驗跟老照片，有機會讓你的故事跟照片出現在我們的網站上唷！<br><br>

  如果你願意提供，請直接與我們聯絡～～<br><br>

  粉專私訊：<br>
  了解更多：
    </div>

    <div>
      <!-- <div class="fb-comments" data-href="https://m.facebook.com/story.php?story_fbid=pfbid0prjapiCSgQEqjUWSqrDh6D2WCZAKRhdWsitWpzbdgW1i1YanugjYfccB5KgpZyMxl&amp;id=1469845916455723" data-width="500" data-numposts="1"></div> -->
    <div class="fb-comments" data-href="https://siddharam.com/" data-width="300" data-colorscheme="light" data-numposts="5"></div>

<!-- <div class="fb-post" data-href="https://m.facebook.com/story.php?story_fbid=pfbid0prjapiCSgQEqjUWSqrDh6D2WCZAKRhdWsitWpzbdgW1i1YanugjYfccB5KgpZyMxl&amp;id=1469845916455723" data-width="500" data-show-text="true"><blockquote cite="https://zh-tw.facebook.com/keelungdumbdiary/posts/1474786975961617" class="fb-xfbml-parse-ignore"><p>這間就是臭粿仔湯，大家應該快流口水了嗎？ 地址：206基隆市七堵區自治街12號</p>由<a href="https://facebook.com/keelungdumbdiary">基隆傻瓜日記</a>發佈於&nbsp;<a href="https://zh-tw.facebook.com/keelungdumbdiary/posts/1474786975961617">2017年8月27日 星期日</a></blockquote></div> -->
<div>aaaaaaaa</div>
<br><div>aaaaaaaa</div>
<br><div>aaaaaaaa</div>
<br><div>aaaaaaaa</div>
<br>

<div class="fb-comments" data-href="https://siddharam.com/1234" data-width="300" data-colorscheme="light" data-numposts="5"></div>

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
      isFBReady: false,
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
  mounted () {
    if(this.isFromIndexPage) {
      location.reload()
    }
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

.under {
  width: 100vw;
  height: calc(100vh - 120px);
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding-top: 120px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-box {
    width: 80%;
    font-size: 24px;
  }
}

</style>
