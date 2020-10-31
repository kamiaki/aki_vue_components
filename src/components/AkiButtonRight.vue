<template>
  <div>
    <!--按钮-->
    <div class="btn" @click="buttonClick">
      <!--内容-->
      <div class="content">
        <div>
          <slot></slot>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
  export default {
    name: "Aki-Button-Right",
    data: function () {
      return {}
    },
    methods: {
      buttonClick() {
        this.$emit('bClick');
      }
    }
  }
</script>

<style scoped>
  .btn {
    background-image: url("../assets/btnright.png");
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
  }

  .content {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
