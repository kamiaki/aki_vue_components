<template>
  <div>
    <!--按钮-->
    <div class="btn" @click="buttonClick">
      <!--内容-->
      <slot></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Aki-Sidebar-Button-1",
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
    background-image: url("../assets/btnsidebar.png");
    width: 100%;
    height: 100%;
    background-repeat: no-repeat;
    background-position: center center;
    background-size: 100% 100%;
    cursor: pointer;
  }
</style>
