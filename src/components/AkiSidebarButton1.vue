<template>
  <div>
    <!--按钮-->
    <div class="btn" @click="buttonClick">
      <div :class="classObject" style=" width: 20%; height: 60%;bottom: 0;left: -10%;"></div>
      <!--内容-->
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Aki-Sidebar-Button-1",
    data: function () {
      return {
        classObject: {
          circle: true,
          turn: false
        }
      }
    },
    methods: {
      buttonClick() {
        let co = this.classObject
        co.turn = true
        this.$emit('bClick');
        setTimeout(function () {
          co.turn = false
        }, 1000)
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
  @keyframes turn{
    0%{-webkit-transform:rotate(0deg);}
    25%{-webkit-transform:rotate(90deg);}
    50%{-webkit-transform:rotate(180deg);}
    75%{-webkit-transform:rotate(270deg);}
    100%{-webkit-transform:rotate(360deg);}
  }
  .turn{
    animation:turn 1s linear infinite;
  }

  .btn {
    background-image: url("../assets/btnsidebar.png");
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
    position: relative;
  }

  .circle {
    background-image: url("../assets/btnsidebar2.png");
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
    position: absolute;
  }
</style>
