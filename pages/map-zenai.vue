<template>
  <div class="map"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="map-row0">
      <img class="map-img" src="@/assets/img/collect/qinai.png" alt="fb">
      <nuxt-link to="/collect">
        <img class="map-img" src="@/assets/img/btn/backmap.png" alt="fb">
      </nuxt-link>
    </div>

    <div class="map-outer">
      <div class="map-left">
        <div @click="currentselect = 0" class="map-box">
          <div class="map-row">
            <div>吳XX</div>
            <div class="map-want">想找</div>
            <div>美食</div>
          </div>
          <div class="map-text">貫鈞豬腳飯</div>
        </div>
        <div @click="currentselect = 1" class="map-box">
          <div class="map-row">
            <div>JoyHsieh</div>
            <div class="map-want">想找</div>
            <div>建築/場所</div>
          </div>
          <div class="map-text">華六街果菜市場公共廁所</div>
        </div>
      </div>
      <div class="map-right">

        <div v-show="currentselect == 0">
          <div class="map-box2">
            <div class="map-row2">
              <div>
                <div class="map-name">吳XX</div>
                <div class="map-row3">
                  <div class="map-want2">想找</div>
                  <div>美食</div>
                </div>
              </div>
              <div class="map-like">
                <div class="fb-like" data-href="https://frankyeah.github.io/disappear/anlei?id=吳閎洧" data-width="300" data-layout="" data-action="" data-size="" data-share="true"></div>
              </div>
            </div>
            <div class="map-text2">曾經吃過一次，驚為天人，後來要再去時就收掉了</div>
            <div class="map-title">我提供的線索</div>
            <a href="https://m.facebook.com/story.php?story_fbid=pfbid02N2qi2n8c6mn7bk4ThVjMGjqotv5nz2JtezG8WjYz2Y5x2X1hAdKcodnDVeyXRNUWl&id=479792885429820&mibextid=qC1gEa" target="_blank" style="color: blue;" class="map-text3">臉書的線索（請點我）</a>
          </div>
          
          <div class="map-fb">
            <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/anlei?id=吳閎洧" data-width="300" data-colorscheme="light" data-numposts="5"></div>
          </div>
        </div>

        <div v-show="currentselect == 1">
          <div class="map-box2">
            <div class="map-row2">
              <div>
                <div class="map-name">JoyHsieh</div>
                <div class="map-row3">
                  <div class="map-want2">想找</div>
                  <div>建築/場所</div>
                </div>
              </div>
              <div class="map-like">
                <div class="fb-like" data-href="https://frankyeah.github.io/disappear/anlei?id=JoyHsieh" data-width="300" data-layout="" data-action="" data-size="" data-share="true"></div>
              </div>
            </div>
            <div class="map-text2">小時候這個公廁的外面，會菜攤堆滿一袋又一袋的洋蔥，每天有好幾個人在那邊剝洋蔥皮，因為這樣一個有特殊味道的地方有設置投幣電話，常常是晚歸人聯絡家人相約等待的所在。</div>
            <div class="map-title">我提供的線索</div>
            <div class="map-text3">一間公共廁所貌，外面堆滿了菜販的菜籃和洋蔥</div>
          </div>
          
          <div class="map-fb">
            <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/anlei?id=JoyHsieh" data-width="300" data-colorscheme="light" data-numposts="5"></div>
          </div>
        </div>




      </div>
    </div>

    <!-- <div class="fb-comments map-fb" data-href="https://siddharam.com/anlei" data-width="300" data-colorscheme="light" data-numposts="5"></div> -->


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
      currentselect: 0,
      isFBReady: false,
      isFromIndexPage: false
    }
  },
    beforeRouteEnter(to, from, next) {
      next(vm => {
      // 判斷是否從首頁過來
      if(from.name) {
      console.log(from.name.substr(0, 5))
        if(from.name.substr(0, 8) == 'collect') {
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



</style>
