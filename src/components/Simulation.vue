<template>
  <div id="sm" class="sm">
    <div class="sm-background">
      <img class="sm-background_img" v-bind:src="baseUrl + bgImg" alt="">
      <img class="sm-product_img" v-bind:src="baseUrl + 'sofa' + colorImg + legImg" alt="">
    </div>
    <div class="sm-detail">
      <p class="sm-detail_cover">カバー色：{{ cover }}</p>
      <p class="sm-detail_leg">脚タイプ：{{ leg }}</p>
      <p class="sm-detail_price">価格：<span>&yen;{{ price | numDelimiter }}</span></p>
    </div>
    <transition>
      <ColorOption class="selectOption" v-show="coverActive" v-bind:color-img="colorImg" />
    </transition>

    <transition>
      <LegOption class="selectOption" v-show="legActive" v-bind:leg-img="legImg" />
    </transition>

    <transition>
      <BgOption class="selectOption" v-show="roomActive" v-bind:bg-img="bgImg" />
    </transition>
    
    <div class="sm-option">
      <ul class="sm-option_list">
        <li class="sm-option_item"><a href="#" v-on:click="coverOptions" class="sm-option_btn"><font-awesome-icon icon="palette" class="icon" /> カバー色</a></li>
        <li class="sm-option_item"><a href="#" v-on:click="legOptions" class="sm-option_btn"><font-awesome-icon icon="couch" class="icon" /> 脚タイプ</a></li>
        <li class="sm-option_item"><a href="#" v-on:click="roomOptions" class="sm-option_btn"><font-awesome-icon icon="street-view" class="icon" /> 背景</a></li>
      </ul>
    </div>

    <div class="sm-des">
      <p class="sm-des_text">セミオーダーソファーのシミュレーションサービスを想定して開発しました。シミューレーション 画像、内奥ともに全てサンプルです。</p>
    </div>
  </div>
</template>

<script>
import ColorOption from '@/components/ColorOption.vue'
import LegOption from '@/components/LegOption.vue'
import BgOption from '@/components/BgOption.vue'
export default {
  name: 'Simulation',
  components: {
    ColorOption,
    LegOption,
    BgOption
  },
  data () {
    return {
      baseUrl: '/img/simulation/',
      bgImg: 'simu_bg01.jpg',
      colorImg: '_red_',
      legImg: 'leg01.png',
      coverActive: false,
      legActive: false,
      roomActive: false,
      price: 20000,
      cover: 'レッド',
      leg: 'ダークブラウン'
    }
  },
  methods: {
    coverOptions: function () {
      this.coverActive = !this.coverActive;
      this.legActive = false;
      this.roomActive = false;
    },
    legOptions: function () {
      this.coverActive = false;
      this.legActive = !this.legActive;
      this.roomActive = false;
    },
    roomOptions: function () {
      this.coverActive = false;
      this.legActive = false;
      this.roomActive = !this.roomActive;
    }
  },
  filters: {
    numDelimiter: function (value) {
      return value.toString().replace(/(\d)(?=(\d{3})+$)/g, '$1,')
    }
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.v-enter-active, .v-leave-active {
  transition: opacity .5s;
}
.v-enter, .v-leave-to {
  opacity: 0;
}
// シミュレーション画像
.sm-background {
  position: relative;
  padding-top: 60vmin;
  @media screen and (min-width: 768px) {
    width: 640px;
    margin: 0 auto;
  }
  img {
    width: 100%;
    height: 100%;
  }
  .sm-background_img {
    position: absolute;
    top: 0;
    left: 0;
  }
  .sm-product_img {
    position: absolute;
    top: 0;
    left: 0;
    z-index: 100;
  }
}
.selectOption {
  position: absolute;
  top: 40%;
  left: 0;
  right: 0;
  z-index: 200;
  background: rgba(24,30,31,0.4);
  width: 90%;
  border-radius: 1rem;
  padding: 5%;
  margin: 0 auto;
  box-sizing: border-box;
}
// シミュレーション文言
.sm-des {
  width: 80%;
  margin: 0 auto;
}
.sm-des_text {
  text-align: left;
  font-size: 1.1rem;
  line-height: 1.6;
}
// フッター選択ナビ
.sm-option_list {
  position: fixed;
  bottom: 0;
  background: #42b983;
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  width: 100%;
}
.sm-option_item {
  width: 33.333%;
  border-right: 1px solid #fff;
  padding: 1.4rem 1rem;
  &:last-child {
    border-right: none;
  }
}
.sm-option_btn {
  text-decoration: none;
  font-weight: bold;
  font-size: 3.8vmin;
  color: #ffffff;
  display: inline-block;
  width: 100%;
  height: auto;
}
.icon {
  font-size: 5.2vmin;
}
//カバー選択
.sm-detail_cover, .sm-detail_leg, .sm-detail_price {
  font-size: 1.3rem;
  font-weight: bold;
}
.sm-detail_price {
  span {
    font-size: 1.4rem;
    color: #CB2131;
  }
}
.sm-color-option_list {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.sm-color-option_item {
  width: 33%;
  border-radius: 2rem;
  padding: 0.6rem;
  margin: 0 0 1rem 0;
  cursor: pointer;
}
.sw-btn_red {
  background: #CB2131;
  color: #fff;
}
.sw-btn_turquoise {
  background: #3BBBAF;
  color: #fff;
}
.sw-btn_orange {
  background: #D75E1B;
  color: #fff;
}
.sw-btn_green {
  background: #5E9E4F;
  color: #fff;
}
.sw-btn_blue {
  background: #7B79E4;
  color: #fff;
}
.sw-btn_black{
  background: #363636;
  color: #fff;
}
</style>
