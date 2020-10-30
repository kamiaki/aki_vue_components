<template>
  <div id="app">
    <Aki-Button-1 style="width: 200px;height: 200px;
    font-size: 50px" @bClick="showMsg(msg)">点击我
    </Aki-Button-1>

    <Aki-Button-2 style="width: 150px;height: 20px;
    font-size: 10px" @bClick="showMsg(msg)">点击我
    </Aki-Button-2>
  </div>
</template>

<script>
  import AkiButton1 from "./components/AkiButton1.vue";
  import AkiButton2 from "./components/AkiButton2.vue";

  export default {
    name: 'app',
    components: {
      AkiButton1,
      AkiButton2
    },
    data() {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    },
    methods: {
      showMsg(msg) {
        alert(msg)
      }
    }
  }
</script>

<style>
</style>
