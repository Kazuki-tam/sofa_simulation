<template>
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
        <div v-on:click="btnClose" class="sm-btn_close">閉じる</div>
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
    },
    turquoiseSelect: function () {
      this.$parent.colorImg = '_turquoise_'
    },
    orangeSelect: function () {
      this.$parent.colorImg = '_orange_'
    },
    greenSelect: function () {
      this.$parent.colorImg = '_green_'
    },
    blueSelect: function () {
      this.$parent.colorImg = '_blue_'
    },
    blackSelect: function () {
      this.$parent.colorImg = '_black_'
    },
    btnClose: function () {
      this.$parent.coverActive = false
    }
  }
}
</script>

<!-- カバー色選択 CSSカプセル化 -->
<style scoped lang="scss">
.sm-color-option {
  position: relative;
}
.sm-btn_close {
  position: absolute;
  top: 0;
  right: 0;
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
