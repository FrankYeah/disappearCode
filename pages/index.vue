<template>
  <div class="index"
    :style="{
      'backgroundImage' : 'url(' + require('@/assets/img/base/a.jpg') + ')'
    }"
  >
    <div class="index-box">
      <div>
        <div v-if="tempDis" class="index-head">{{ disappear[index].name }}</div>
        <div v-if="tempDis" class="index-text" v-html="text"></div>
      </div>
      <img @click="isShowPopup = true" class="index-btn" src="@/assets/img/btn/disappear.png" alt="btn">
    </div>

    <div v-if="isShowPopup" @click="isShowPopup = false" class="index-popup">
      <div @click.stop class="index-popup-box">
        <div class="index-popup-text">消失是...</div>
        <el-input class="index-popup-input" v-model="inputText" maxlength="10" show-word-limit placeholder="投件於網頁顯示暱稱"></el-input>
        <el-input
          class="index-popup-textarea"
          type="textarea"
          maxlength="150"
          show-word-limit
          :autosize="{ minRows: 5, maxRows: 10}"
          placeholder="消失是什麼...（十行後不顯示）"
          v-model="textareaText">
        </el-input>
        <!--  -->
        <div class="index-popup-btn-box">
          <img @click="send" class="index-popup-btn" src="@/assets/img/btn/project-article.png" alt="btn">
        </div>
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
      tempDis: false,
      inputText: '',
      textareaText: '',
      isShowPopup: false,
      textIn: false,
      index: 0,
      text: "",

      disappear: [
        { 
          name: '[城市少女]',
          text: `【LINE對話】
            媽：ＸＸＸ去倒垃圾
            我：等
            我：我在忙
            媽：現在
            媽：不要等
            媽：等等
            媽：垃圾車跑掉
            我：你去
            媽：什麼我去
            媽：開門
            我：我就在忙
            媽：用講的
            媽：開門用講的
          `
        },
        { 
          name: '［活在科技時代的我］',
          text: `科技創造人與人之間的多元連結，
            但也悄悄地使人與人的連結
            逐步消失⋯⋯
          `
        },
        { 
          name: '[雨]',
          text: `一二三
          木頭人
          轉過身
          才發現
          那習慣
          某一天
          已改變
          `
        },
        { 
          name: '[艾力克斯]',
          text: `以前
          和朋友見面
          看見的是彼此臉上的溫度
          現在
          和朋友見面
          看見的只有手上冰冷的螢幕
          `
        },
        { 
          name: '[HIKARI]',
          text: `回憶的蹉跎，消失了的是時間`
        },
        { 
          name: '［眉］',
          text: `曾經的周遭景物，
            陪伴著我們的回憶，
            這樣的消失令人懷念，
            我們懷念的是那時的景色，
            還是那時的我們？
          `
        },
        { 
          name: '[路人甲]',
          text: `嗯沒關係
            過兩天就會習慣了吧
            只是偶爾想起來
            覺得這裡有點空空的
          `
        },
        { 
          name: '[阿杜]',
          text: `五年
            十年
            二十年
            走過相同的路
            為的不是看見那些早已不同的風景
            而是細細品嘗埋藏在回憶裡的人情
          `
        },
        { 
          name: '[句點王]',
          text: `如果這世界『  』消失了`
        },
        { 
          name: '［感嘆的老人］',
          text: `隨著時間流逝，
          身邊的好友、親人來來去去，
          我依舊在這，
          我真的依舊在嗎？
          `
        },
        { 
          name: '[...]',
          text: `我以為的消失是全世界與我一起
          其實並不
          不過是我一個人的失去
          地球繼續自轉
          世界一點也沒有停下腳步
          消失的
          是我而已
          `
        },
        { 
          name: '[DoDo]',
          text: `有人說
          人啊
          是透過自己與他人的記憶拼湊出來的
          這麼說來
          如果某個他人消失了
          是不是自己的某一部分
          也就跟著被遺忘了呢
          `
        },
        { 
          name: '[王維]',
          text: `在消失之前，以詩銘刻所有，我們沒有忘記。`
        },
        { 
          name: '[自問自答]',
          text: `好久不見，你好嗎？`
        },
        { 
          name: '[異鄉人]',
          text: `消失？一但存在心中便是永恆`
        },
        { 
          name: '[未來]',
          text: `消失不是盡頭
            更像是某個時間節點
            讓人知道那人事物不在那裡了
            消失的青春
            消失的車站
            消失的信念
            不論消失了什麼
            我們同樣感傷
            並以消失唱名
            作為懷念
          `
        },
        { 
          name: '[寂寞人]',
          text: `「城市突然不一樣了，
            氣味與色調也不一樣了，
            多了些什麼，也少了些什麼。

            人群行走的方向突然不一樣了，
            眼底的事物也不一樣了，
            閃爍了什麼，也黯淡了什麼。

            大山大海還躺在那，
            小貓小狗也還睡著，
            可能某個突然，就不知道跑去哪兒了。

            或許，不是突然，而是進行著。」
          `
        }
      ]
    }
  },
  async mounted () {
    this.showText()
  },
  destroyed () {
    
  },
  computed: {
    
  },
  methods: {
    showText() {
      this.index = Math.floor(Math.random()*this.disappear.length)
      this.text = ""
      let index = 0
      if(this.textIn) {
        this.index = this.disappear.length-1
        this.textIn = false
      }
      this.tempDis = true
      const timer = setInterval(() => {
        this.text += this.disappear[this.index].text[index]
        index++
        if (index === this.disappear[this.index].text.length) {
          clearInterval(timer)
          setTimeout(() => {
            this.index = (this.index + 1) % this.disappear.length
            this.showText()
          }, 3000)
        }
      }, 100);
    },
    send() {
      // 以斷行分割字串，並移除空白字元
      const lines = this.textareaText.trim().split('\n').map(line => line.trim());

      // 限制每行最多15個字，多餘的字斷行
      const processedLines = lines.reduce((acc, line) => {
        const lineChars = line.split('');
        let currentLine = '';
        for (let i = 0; i < lineChars.length; i++) {
          if (currentLine.length === 15) {
            acc.push(currentLine);
            currentLine = '';
          }
          currentLine += lineChars[i];
          if (i === lineChars.length - 1 && currentLine.length > 0) {
            acc.push(currentLine);
          }
        }
        return acc;
      }, []);

      // 最多回傳10段，其他刪除
      const limitedLines = processedLines.slice(0, 10);

      // 回傳字串，以斷行分隔每行
      this.textareaText = limitedLines.join('\n');

      this.disappear.push({
        name: this.inputText,
        text: this.textareaText
      })
      this.inputText = ''
      this.textareaText = ''
      this.textIn = true
      this.isShowPopup = false
    }
  },
  watch: {
    
  }
}
</script>

<style lang="scss" scoped>

.index {
  width: 100vw;
  min-height: calc(100vh - 120px);
  display: flex;
  justify-content: center;
  padding-top: 120px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position-x: center;
  background-position-y: center;
  color: white;

  &-box {
    display: flex;
    justify-content: space-between;
    width: 80%;
    height: 80%;
  }

  &-head {
    margin: 20px 0px 30px 0px;
    font-size: 24px;
  }

  &-text {
    margin-top: 20px;
    white-space: pre-line;
    font-size: 18px;
    letter-spacing: 1.3px;
  }

  &-btn {
    width: 200px;
    height: 100px;
    margin-top: 35%;
    cursor: pointer;
    opacity: 0.6;

    &:hover {
      opacity: 1;
    }
  }

  &-popup {
    position: fixed;
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1;

    &-box {
      width: 500px;
      padding: 40px 40px 60px;
      background-color: rgba(0, 0, 0, 0.7);
    }

    &-text {
      font-size: 32px;
    }

    &-input {
      margin-top: 20px;
      font-size: 24px;
    }

    &-textarea {
      margin-top: 20px;
      font-size: 18px;
    }

    &-btn-box {
      text-align: center;
    }

    &-btn {
      width: 130px;
      height: 88px;
      cursor: pointer;
      opacity: 0.6;

      &:hover {
        opacity: 1;
      }
      
    }
    
  }
}

@media( max-width: 1023px ){

.index {
  padding: 80px 0px 40px;

  &-box {
    position: relative;
    flex-direction: column;
    width: 90%;
    min-height: calc(100vh - 90px);
    height: 100%;
  }

  &-head {
    margin: 20px 0px 20px 0px;
    font-size: 20px;
  }

  &-text {
    margin-top: 0px;
    font-size: 16px;
  }

  &-btn {
    position: absolute;
    right: 0px;
    bottom: 10px;
    width: 100px;
    height: 50px;
    margin-top: 20px;
  }

  &-popup {

    &-box {
      width: 90%;
      padding: 60px 20px 0px;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
    }

    &-text {
      
    }

    &-input {
      
    }

    &-textarea {
      
    }

    &-btn-box {
      
    }

    &-btn {
    }
    
  }
}

}

</style>
