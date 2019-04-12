<template>
  <section>
      <div class="sm-leg-option">
        <h2>脚タイプ</h2>
        <ul class="sm-leg-option_list">
          <li v-on:click="leg01Select" class="sm-leg-option_item sw-btn_darkbrown">ダーク<br>ブラウン</li>
          <li v-on:click="leg02Select" class="sm-leg-option_item sw-btn_ashgray">アッシュ<br>グレイ</li>
        </ul>
        <div v-on:click="btnClose" class="sm-btn_close">閉じる</div>
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
    },
    leg02Select: function () {
      this.$parent.legImg = 'leg02.png'
    },
    btnClose: function () {
      this.$parent.legActive = false
    }
  }
}
</script>

<!-- カバー色選択 CSSカプセル化 -->
<style scoped lang="scss">
.sm-leg-option {
  position: relative;
}
.sm-btn_close {
  position: absolute;
  top: 0;
  right: 0;
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
  padding: 0.6rem;
  margin: 0 0 1rem 0;
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
