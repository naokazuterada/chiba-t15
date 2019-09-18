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
  font-family: '游ゴシック体', 'Yu Gothic', 'YuGothic', YuGothic, 'Lucida Grande','Hiragino Kaku Gothic Pro','ヒラギノ角ゴ Pro W3','HiraKakuProN-W3','メイリオ','Meiryo','ＭＳ ゴシック','MS Gothic',Osaka,Verdana,arial,helvetica,sans-serif;
}

.pre,
  .days {
    font-size: 12vh;
    font-weight: bold;
  }
  .num {
    font-size: 45vh;
    line-height: 1em;
  }

/* 横長の時　*/
@media screen and (orientation: portrait) {
  .pre,
  .days {
    font-size: 13vw;
    font-weight: bold;
  }
  .num {
    font-size: 55vw;
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