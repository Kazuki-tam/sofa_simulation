<template>
  <section>
      <div class="sm-leg-option">
        <h2 class="sm-option_title">脚タイプ</h2>
        <ul class="sm-leg-option_list">
          <li v-on:click="leg01Select" class="sm-leg-option_item sw-btn_darkbrown">ダーク<br>ブラウン</li>
          <li v-on:click="leg02Select" class="sm-leg-option_item sw-btn_ashgray">アッシュ<br>グレイ</li>
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
  name: 'LegOption',
  props: {
    legImg: [String, Number],
    legActive: Boolean
    },
  methods: {
    leg01Select: function () {
      this.$parent.legImg = 'leg01.png'
      this.$parent.leg = 'ダークブラウン'
    },
    leg02Select: function () {
      this.$parent.legImg = 'leg02.png'
      this.$parent.leg = 'アッシュグレイ'
    },
    btnClose: function () {
      this.$parent.legActive = false
    }
  }
}
</script>

<!-- 脚タイプ選択 CSSカプセル化 -->
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
.sm-leg-option {
  position: relative;
}
.sm-leg-option_list {
  list-style: none;
  padding: 0;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.sm-leg-option_item {
  width: 33%;
  border-radius: 2rem;
  padding: 0.8rem 0.6rem;
  margin: 0 0 1rem 0;
  font-size: 1.2rem;
  cursor: pointer;
}
.sw-btn_darkbrown {
  background: #4A3A3A;
  color: #fff;
}
.sw-btn_ashgray{
  background: #747578;
  color: #fff;
}
</style>
