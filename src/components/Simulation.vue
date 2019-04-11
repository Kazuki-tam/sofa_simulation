<template>
  <div id="sm" class="sm">
    <div class="sm-background">
      <img class="sm-background_img" v-bind:src="baseUrl + bgImg" alt="">
      <img class="sm-product_img" v-bind:src="baseUrl + 'sofa' + colorImg + legImg" alt="">
    </div>
    <div class="sm-detail">
      <p class="sm-detail_price">価格：&yen;{{ price[1] }}</p>
      <p class="sm-detail_cover">カバー色：{{ cover }}</p>
      <p class="sm-detail_leg">脚タイプ：{{ leg }}</p>
    </div>
    <div class="sm-option">
      <button class="sm-option_btn">カバー色</button>
      <button class="sm-option_btn">脚タイプ</button>
      <button class="sm-option_btn">部屋</button>
    </div>

    <section>
      <div class="sm-color-option">
        <h2>カバー色</h2>
        <ul class="sm-color-option_list">
          <li v-on:click="redSelect" class="sm-color-option_item sw-btn_red">レッド</li>
          <li v-on:click="turquoiseSelect" class="sm-color-option_item sw-btn_turquoise">ターコイズ</li>
          <li v-on:click="orangeSelect" class="sm-color-option_item sw-btn_orange">オレンジ</li>
          <li v-on:click="greenSelect" class="sm-color-option_item sw-btn_green">グリーン</li>
          <li v-on:click="blueSelect" class="sm-color-option_item sw-btn_blue">ブルー</li>
          <li v-on:click="blackSelect" class="sm-color-option_item sw-btn_black">ブラック</li>
        </ul>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Simulation',
  data () {
    return {
      baseUrl: '/img/simulation/',
      bgImg: 'simu_bg01.jpg',
      colorImg: '_red_',
      legImg: 'leg01.png',
      price: [1000, 2000],
      cover: 'レッド',
      leg: 'ダークブラウン'
    }
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.sm-background {
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
.sm-option_btn {
  background: #42b983;
  color: #ffffff;
  border-radius: 2rem;
  padding: 1rem;
  margin-bottom: 1rem;
  display: inline-block;
  border: none;
  width: 40%;
  &:first-child {
    margin-right: 5%;
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
