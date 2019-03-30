<template>
  <main>
    <div class="show_text">
      <div class="show_Text" v-bind:style="{left:leftX}">
        <div id="Text_top">当前价格:￥{{value}}</div>
        <div id="Text_bottom"></div>
      </div>
    </div>
    <!--显示条-->
    <div class="Display_bar">
      <div class="progress_bar" v-bind:style="{width:toPercent}"></div>
      <div class="down_bar"></div>
      <div class="down_bar"></div>
    </div>
    <div class="Original_price">
      <p>￥1000</p>
      <p>(原价)</p>
    </div>
    <div class="Reserve_price">
      <p>￥500</p>
      <p>(可购买)</p>
    </div>
    <div class="Reserve_price">
      <p>￥100</p>
      <p>(底价)</p>
    </div>
  </main>
</template>
<script>
  export default {
    props: ['value'],
    name: 'show',
    data() {
      return {}
    },
    computed: {
      toPercent: function () {
        if (this.value > 1000 || this.value < 0) {
          return
        } else {
          var number = 100 - this.value / 10;
          number = number + "%";
          return number;
        }
      },
      leftX: function () {
        var leftX = 627 + "px";
        if (this.value > 1000 || this.value < 0) {
          return leftX
        } else {
          leftX = (1 - this.value / 1000) * 692 - 65;
          leftX = leftX + "px";
          return leftX
        }
      }
    }
  }
</script>
<style>
  .show_text {
    width: 100%;
    height: 53px;
    position: relative;
    /*background-color: aqua;*/
  }

  .show_Text {
    position: absolute;
    width: 130px;
    height: 53px;
    display: flex;
    flex-direction: column;
    /*background: #FF573A;*/
    border-radius: 5px;
  }

  #Text_top {
    width: 130px;
    height: 36px;
    background: #FF573A;
    font-family: PingFangSC-Regular;
    font-size: 16px;
    color: #FFFFFF;
    text-align: center;
    line-height: 36px;
  }

  #Text_bottom {
    margin-left: 55px;
    width: 0;
    height: 0;
    border-width: 10px;
    border-style: solid;
    border-color: #FF573A transparent transparent transparent;
  }
</style>
