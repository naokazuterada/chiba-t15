<template>
  <div class="wrap">
    <span class="pre">台風から</span>
    <span class="num">{{ day }}</span>
    <span class="days">日目</span>
  </div>
</template>

<style>
.wrap {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: column;
  text-align: center;
  font-family: "游ゴシック" , "Yu Gothic" , "游ゴシック体" , "YuGothic" , "ヒラギノ角ゴ Pro W3" , "Hiragino Kaku Gothic Pro" , "Meiryo UI" , "メイリオ" , Meiryo , "ＭＳ Ｐゴシック" , "MS PGothic" , sans-serif;
}

.pre,
.days {
  font-size: 13vw;
  font-weight: bold;
}
.num {
  font-size: 65vw;
  line-height: 1em;
}

@media screen and (orientation: landscape) {
  .pre,
  .days {
    font-size: 13vh;
    font-weight: bold;
  }
  .num {
    font-size: 50vh;
    line-height: 1em;
  }
}
</style>

<script>
import moment from 'moment'

export default {
  props: {
    day: {
      type: String,
      required: true
    }
  },
  mounted: function(){
    this.day = moment().diff(moment('2019-09-09'), 'days');
  }
}
</script>