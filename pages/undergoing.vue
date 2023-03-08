<template>
  <div class="under"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/index/bg3.png') + ')'
    }"
  >
    <div class="under-title">
      <div>【專案】十八羅漢洞</div>
      <a class="under-href" href="https://forms.gle/aNXgxpgJnC616pu86" target="_blank">
        <div class="under-underline">提供老照片處</div>
        <img class="under-img" src="@/assets/img/social/link.png" alt="fb">
      </a>
    </div>

    <div class="under-inner under-desktop">
      <div :class="['under-box', {'under-box-select': currentReport == index}]"
        v-for="(report, index) in reports"
        :key="index"
         @click="currentReport = index"
      >
        <div class="under-date">{{ report.date }}</div>
        <div class="under-head">{{ report.head }}</div>
      </div>
    </div>
    <div class="under-text under-desktop" v-html="reports[currentReport].text"></div>

    <div class="under-drawer under-rwd">
      <div class="under-drawer-box" 
        v-for="(report, index) in reports"
        :key="index"
        @click="report.isShow = !report.isShow"
      >
        <div class="under-box">
          <div class="under-date">{{ report.date }}</div>
          <div class="under-head">{{ report.head }}</div>
        </div>
        <div v-if="report.isShow" class="under-text">{{ report.text }}</div>
      </div>
    </div>

    <div class="under-fb">
      <div class="under-fb-head">開放留言協尋資料：</div>
      <!-- <div class="fb-comments" data-href="https://m.facebook.com/story.php?story_fbid=pfbid0prjapiCSgQEqjUWSqrDh6D2WCZAKRhdWsitWpzbdgW1i1YanugjYfccB5KgpZyMxl&amp;id=1469845916455723" data-width="500" data-numposts="1"></div> -->
      <div class="under-comments">
        <div class="fb-comments" data-href="https://frankyeah.github.io/disappear/undergoing?id=0" data-width="100vw" data-colorscheme="light" data-numposts="5"></div>
      </div>
      <!-- <div class="fb-post" data-href="https://m.facebook.com/story.php?story_fbid=pfbid0prjapiCSgQEqjUWSqrDh6D2WCZAKRhdWsitWpzbdgW1i1YanugjYfccB5KgpZyMxl&amp;id=1469845916455723" data-width="500" data-show-text="true"><blockquote cite="https://zh-tw.facebook.com/keelungdumbdiary/posts/1474786975961617" class="fb-xfbml-parse-ignore"><p>這間就是臭粿仔湯，大家應該快流口水了嗎？ 地址：206基隆市七堵區自治街12號</p>由<a href="https://facebook.com/keelungdumbdiary">基隆傻瓜日記</a>發佈於&nbsp;<a href="https://zh-tw.facebook.com/keelungdumbdiary/posts/1474786975961617">2017年8月27日 星期日</a></blockquote></div> -->
      <!-- <div class="fb-comments" data-href="https://siddharam.com/1234" data-width="300" data-colorscheme="light" data-numposts="5"></div> -->
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
      isFromIndexPage: false,
      currentReport: 0,
      reports: [
        {
          isShow: false,
          date: '2022年5月',
          head: '「十八羅漢洞」？',
          text: `雞籠怪奇團隊以「消失」作為主題，發想團隊想挑戰的新計畫，其中一組成員很快地鎖定主題「十八羅漢洞」，原因為此地傳言多、實證少，據傳已封洞無法進入了；怪奇團隊幾乎是80~90年次的青年，未曾入洞但聞其名的人佔多數，因此非常好奇。`
        },
        {
          isShow: false,
          date: '2022年7月',
          head: '好奇心爆棚，鎖定主題',
          text: '經過初步網路搜尋，看到基隆人各大社團貼出的內部老照片，許多網友暴風回應，大多分享「很恐怖」「裡面很陰暗、人像會動」「有噴火跟灑水」⋯⋯等，我們對於這些記憶的形容感到非常好奇，究竟是什麼樣的地方，可以讓人驚心膽跳，卻又不捨說再見呢？因此鎖定十八羅漢洞為「消失事務所」的第一件調查事件。'
        },
        {
          isShow: false,
          date: '2022年8月',
          head: '初訪十八羅漢洞',
          text: `
          決定開啟搜查後，事務所立即安排了初次探訪，以確認十八羅漢洞現下實際情況。網路資料顯示：「十八羅漢洞於民國85年因賀伯颱風導致洞內坍塌而封閉至今。」，我們抵達現場後發現果然入口處已封閉，戶外大型千手觀音蓮花池及紅牛皆尚在，旁邊的「聖濟宮」也因疫情影響而暫不開放。在探訪雲龍山（十八羅漢洞的山體）的時候，一旁馬路不時有運動的民眾來回散步，似乎已成當地居民的一種習慣，我們隨機訪問運動的民眾，都得到同樣的回應：「對呀以前十八羅漢洞就在這裡，但很早以前就封起來了。」而原因都是：「不知道、不清楚。」。第一次探訪以失敗告終，帶著好奇心，我們計畫著下一次的探訪。
          `
        },
        {
          isShow: false,
          date: '2022年9月',
          head: '再訪十八羅漢洞',
          text: '期間我們幸運訪得《聖濟宮沿革誌》一書，從書中確定了十八羅漢洞隸屬於聖濟宮，並由三沙灣士紳（中醫師）郭氏家族所建造經營，書中記錄了聖濟宮的建造史、雲龍山及聖濟宮名稱由來；此外也從網路搜得山洞內部情況，看見網友們所說「恐怖人偶」的廬山真面目，原來是忠孝仁愛的代表人物及典故呈現。在古今影像齊全的情況下，得以略作今昔比對，因此事務所計畫將採集到的資料，寫成一篇專欄文章，填補網路上不足資訊，也破解部分靈異謠言。'
        },
        {
          isShow: false,
          date: '2022年10月',
          head: '尋訪三沙灣、完成專欄文章',
          text: '關於建造始末及郭老中醫的傳奇故事，資料已足夠，但關於當地居民記憶，以及當時熱鬧情景，略有不足，因此事務所安排了一次三沙灣地區尋訪，隨機訪問當地居民對於十八羅漢洞的記憶，幸而訪問到當地耆老李大哥（當時恰巧住在聖濟宮下方的民房），得知一些當時建造趣聞。也透過這次尋訪，感受到當地人無不知曉順泰堂郭老中醫善舉事蹟，以及回憶十八羅漢洞時，眼中激起興奮的微光，完成了專欄文章撰寫：（網址連結？）原搜查計畫應到此結束，但這整段歷程的所見所聞，令我們也產生出一股不捨，我們進入深沉地思考與討論。'
        },
        {
          isShow: false,
          date: '2022年11月',
          head: '開啟新任務：辦展覽',
          text: `
            究竟「消失」代表著什麼？十八羅漢洞還在，它只是不再開放了，那這樣算「消失」嗎？<br>
            面對這樣的局面，事務所又能夠做些什麼呢？<br>
            有人說：「真正的消失是被遺忘。」<br>
            有人說：「希望消失前能好好道別。」也有人說：「能夠借此機會再次回憶也很美好。」<br>
            十八羅漢洞對大家而言究竟是怎麼樣的存在呢？<br>
            對此，事務所的大家期待能在結案前，舉辦一場展覽，能夠試著再現十八羅漢洞的洞內風光，也希望透過展覽來與民眾產生對話，無論是曾經進入洞內的人，或是僅聽聞此地的人，都可以用自己的角度談談「十八羅漢洞」、談談「消失」。
          `
        },
        {
          isShow: false,
          date: '2023年1月',
          head: '再訪三沙灣尋找老照片',
          text: '為了策展需求，成員開始收集老照片，希望能在展覽時喚起更多人當年的記憶，我們再次尋訪三沙灣，並聯繫里長協助，但年代久遠，且當地居民逛十八羅漢洞宛如走灶腳一樣，不曾想到要拍照，實在沒有留下老照片，眼看機會渺茫，卻在面臨開會的最後一天，皇天不負苦心人，覓得當時曾入洞製作人偶的工藝師，尋得三張1985年的老照片。'
        },
        {
          isShow: false,
          date: '2023年2月',
          head: '公開募集老照片',
          text: `
          大家小時候有去過十八羅漢洞嗎🤔<br><br>

          基隆人小時候必去探險或是校外教學的地方！聽說裡面有很多神秘雕像跟民間傳說故事～好好奇哦！<br><br>

          網路上的資料很有限，除了之前很多網友分享的文章以外，不曉得大家有沒有自己曾經去過的老照片、或是有趣的故事可以分享呢？<br><br>

          雞籠怪奇團隊現在正在挖掘十八羅漢洞的故事～強力徵求十八羅漢洞的經驗跟老照片，有機會讓你的故事跟照片出現在我們的網站上唷！<br><br>

          請點選頁面上方，投遞老照片：）<br><br>
          `
        },
        {
          isShow: false,
          date: '2023年？月',
          head: '特展 Coming Soon',
          text: '將陸續公開'
        }
      ]
    }
  },
    beforeRouteEnter(to, from, next) {
      next(vm => {
      // 判斷是否從首頁過來
      if(from.name) {
      console.log(from.name.substr(0, 5))
        if(from.name.substr(0, 8) == 'entry') {
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
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 120px 0px 0px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-desktop {
    display: block;
  }

  &-rwd {
    display: none;
  }

  &-title {
    padding: 0px 0px 40px;
    font-size: 24px;
    text-align: center;
  }

  &-href {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 4px;
  }

  &-underline {
    text-decoration: underline;
  }

  &-img {
    width: 20px;
    margin-left: 10px;
  }

  &-inner {
    width: 95%;
    font-size: 24px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  &-box {
    margin: 0px 10px 20px;
    padding: 20px;
    border: 1px solid rgba(white, 0.8);
    cursor: pointer;

    &:hover {
      opacity: 0.8;
    }
  }

  &-box-select {
    background-color: white;
    color: black;
  }

  &-date {
    font-size: 16px;
  }

  &-head {
    font-size: 18px;
  }

  &-text {
    min-height: 200px;
    padding: 0px 200px;
    letter-spacing: 1.3px;
    line-height: 1.5;
    font-size: 18px;
  }

  &-drawer {

  }

  &-drawer-box {

  }

  &-fb {
    width: 100vw;
    padding-bottom: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color: grey;
  }

  &-fb-head {
    padding: 40px 0px;
    font-size: 24px;
  }

  &-comments {
    width: 600px;
  }
}

@media( max-width: 1023px ){

.under {
  padding: 100px 0px 0px;

  &-desktop {
    display: none;
  }

  &-rwd {
    display: block;
  }

  &-title {
    padding: 0px 0px 20px;
    font-size: 20px;
  }

  &-inner {
    width: 100%;
    font-size: 20px;
  }

  &-box {
    margin: 0px 5px 10px;
    padding: 5px;
  }

  &-box-select {
    
  }

  &-date {
    
  }

  &-head {
    
  }

  &-text {
    min-height: 0px;
    padding: 20px 20px;
    font-size: 16px;
  }

  &-drawer {
    width: 90%;
    margin: 0px 0px 30px;
  }

  &-drawer-box {

  }

  &-fb {
    
  }

  &-fb-head {
    padding: 20px 0px;
    font-size: 20px;
  }

  &-comments {
    width: 100%;
  }
}

}

</style>
