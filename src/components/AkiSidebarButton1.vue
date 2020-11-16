<template>
  <div>
    <!--按钮-->
    <div class="btn" :class="{btnImg1: !clicked,btnImg2: clicked}" @click="buttonClick">
      <div class="circle" :class="{'turn': turn, circlImg1: !clicked, circlImg2: clicked}" :style="circleStyle"></div>
      <!--内容-->
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Aki-Sidebar-Button-1",
    props: ['circleStyle','clicked'],
    data: function () {
      return {
        turn: false
      }
    },
    methods: {
      buttonClick() {
        this.$emit('bClick');
        let v = this
        v.turn = true
        setTimeout(function () {
          v.turn = false
        }, 500)
      }
    }
  }
</script>

<style scoped>
  /*
      turn : 定义的动画名称
      1s : 动画时间
      linear : 动画以何种运行轨迹完成一个周期
      infinite :规定动画应该无限次播放
     */
  @keyframes turn {
    0% {
      -webkit-transform: rotate(0deg);
    }
    25% {
      -webkit-transform: rotate(90deg);
    }
    50% {
      -webkit-transform: rotate(180deg);
    }
    75% {
      -webkit-transform: rotate(270deg);
    }
    100% {
      -webkit-transform: rotate(360deg);
    }
  }

  .turn {
    animation: turn 0.5s linear infinite;
  }

  .btnImg1{
    background-image: url("../assets/btnsidebar.png");
  }
  .btnImg2{
    background-image: url("../assets/btnsidebar_c.png");
  }

  .btn {
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
    position: relative;
  }

  .circlImg1{
    background-image: url("../assets/btnsidebar2.png");
  }
  .circlImg2{
    background-image: url("../assets/btnsidebar2_c.png");
  }

  .circle {
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
    position: absolute;
  }
</style>
