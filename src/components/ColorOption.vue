<template>
  <section>
      <div class="sm-color-option">
        <h2 class="sm-option_title">カバー色</h2>
        <ul class="sm-color-option_list">
          <li v-on:click="redSelect" class="sm-color-option_item sw-btn_red">レッド</li>
          <li v-on:click="turquoiseSelect" class="sm-color-option_item sw-btn_turquoise">ターコイズ</li>
          <li v-on:click="orangeSelect" class="sm-color-option_item sw-btn_orange">オレンジ</li>
          <li v-on:click="greenSelect" class="sm-color-option_item sw-btn_green">グリーン</li>
          <li v-on:click="blueSelect" class="sm-color-option_item sw-btn_blue">ブルー</li>
          <li v-on:click="blackSelect" class="sm-color-option_item sw-btn_black">ブラック</li>
        </ul>
        <div v-on:click="btnClose" class="sm-btn_close">
          <div class="sm-btn_close_line"></div>
          <div class="sm-btn_close_line"></div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  name: 'ColorOption',
  props: {
    colorImg: [String, Number],
    coverActive: Boolean
    },
  methods: {
    redSelect: function () {
      this.$parent.colorImg = '_red_'
      this.$parent.cover = 'レッド'
    },
    turquoiseSelect: function () {
      this.$parent.colorImg = '_turquoise_'
      this.$parent.cover = 'ターコイズ'
      this.$parent.price = 21000
    },
    orangeSelect: function () {
      this.$parent.colorImg = '_orange_'
      this.$parent.cover = 'オレンジ'
      this.$parent.price = 22000
    },
    greenSelect: function () {
      this.$parent.colorImg = '_green_'
      this.$parent.cover = 'グリーン'
      this.$parent.price = 23000
    },
    blueSelect: function () {
      this.$parent.colorImg = '_blue_'
      this.$parent.cover = 'ブルー'
      this.$parent.price = 24000
    },
    blackSelect: function () {
      this.$parent.colorImg = '_black_'
      this.$parent.cover = 'ブラック'
      this.$parent.price = 20000
    },
    btnClose: function () {
      this.$parent.coverActive = false
    }
  }
}
</script>

<!-- カバー色選択 CSSカプセル化 -->
<style scoped lang="scss">
// シミュレーション開閉
.sm-btn_close {
  position: absolute;
  top: -1.6rem;
  right: 1.6rem;
}
.sm-btn_close_line {
  width: 2rem;
  height: 3px;
  position: absolute;
  top: 2rem;
  bottom: 0;
  right: 0;
  left: 0;
  background: #ffffff;
  &:nth-child(1) {
    transform:translateY(0) rotate(-45deg);
  }
  &:nth-child(2) {
   transform:translateY(0) rotate(45deg);
  }
}
.sm-color-option {
  position: relative;
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
  padding: 0.8rem 0.6rem;
  margin: 0 0 1rem 0;
  font-size: 1.2rem;
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
