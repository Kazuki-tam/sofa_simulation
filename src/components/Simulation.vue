<template>
  <div id="sm" class="sm">
    <div class="sm-background">
      <img class="sm-background_img" v-bind:src="baseUrl + bgImg" alt="">
      <img class="sm-product_img" v-bind:src="baseUrl + 'sofa' + colorImg + legImg" alt="">
    </div>
    <div class="sm-detail">
      <p class="sm-detail_cover">カバー色：{{ cover }}</p>
      <p class="sm-detail_leg">脚タイプ：{{ leg }}</p>
      <p class="sm-detail_price">価格：&yen;{{ price[1] }}</p>
    </div>
    <ColorOption class="selectOption" v-show="coverActive" v-bind:color-img="colorImg" />
    <LegOption class="selectOption" v-show="legActive" v-bind:leg-img="legImg" />
    <BgOption class="selectOption" v-show="roomActive" v-bind:bg-img="bgImg" />

    <div class="sm-option">
      <ul class="sm-option_list">
        <li class="sm-option_item"><a href="#" v-on:click="coverOptions" class="sm-option_btn"><font-awesome-icon icon="palette" class="icon" /> カバー色</a></li>
        <li class="sm-option_item"><a href="#" v-on:click="legOptions" class="sm-option_btn"><font-awesome-icon icon="couch" class="icon" /> 脚タイプ</a></li>
        <li class="sm-option_item"><a href="#" v-on:click="roomOptions" class="sm-option_btn"><font-awesome-icon icon="street-view" class="icon" /> 背景</a></li>
      </ul>
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
      price: [1000, 2000],
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
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.sm-background {
  // シミュレーション画像
  position: relative;
  padding-top: 60vmin;
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
  background: rgba(255,255,255,0.8);
  width: 100%;
  padding: 5%;
  margin: 0 auto;
  box-sizing: border-box;
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
  padding: 1rem;
  &:last-child {
    border-right: none;
  }
}
.sm-option_btn {
  text-decoration: none;
  font-weight: bold;
  font-size: 1rem;
  color: #ffffff;
  display: inline-block;
}
.icon {
  font-size: 1.2rem;
}
//カバー選択
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
