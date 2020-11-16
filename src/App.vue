<template>
  <div id="app">
    <Aki-Button-1 style="width: 150px;height: 50px;
    font-size: 50px" @bClick="showMsg(msg)">点击我
    </Aki-Button-1>

    <Aki-Button-2 style="width: 150px;height: 50px;
    font-size: 10px" @bClick="showMsg(msg)">点击我
    </Aki-Button-2>

    <AkiButtonLeft style="width: 150px;height: 50px;
    font-size: 10px" @bClick="showMsg(msg)">点击我
    </AkiButtonLeft>

    <AkiButtonRight style="width: 150px;height: 50px;
    font-size: 10px" @bClick="showMsg(msg)">点击我
    </AkiButtonRight>

    <!--例用循环来拿到index 染色-->
    <AkiSidebarButton1
      v-for="(obj,index) in btnlist" :key="index"
      :clicked="index === clickIndex"
      :circleStyle="{width: '30px',height: '30px',bottom: '-0px',left: '-8px'}"
      style="width: 200px;height: 50px;" @bClick="showMsg(msg),clickBtn(index)">
      <div style="font-size: 20px;text-align: center;line-height: 40px;color: #000dff">{{obj.text}}</div>
    </AkiSidebarButton1>

  </div>
</template>

<script>
  import AkiButton1 from "./components/AkiButton1.vue";
  import AkiButton2 from "./components/AkiButton2.vue";
  import AkiButtonLeft from "./components/AkiButtonLeft";
  import AkiButtonRight from "./components/AkiButtonRight";
  import AkiSidebarButton1 from "./components/AkiSidebarButton1";

  const bl = [
    {text: '点击我1', url: 'url1'}, {text: '点击我2', url: 'url2'}, {text: '点击我3', url: 'url3'}
  ]

  export default {
    name: 'app',
    components: {
      AkiButtonRight,
      AkiButtonLeft,
      AkiButton1,
      AkiButton2,
      AkiSidebarButton1
    },
    data() {
      return {
        clickIndex: undefined,
        btnlist: bl,
        msg: 'Welcome to Your Vue.js App'
      }
    },
    methods: {
      clickBtn(index) {
        this.clickIndex = index
      },
      showMsg(msg) {
        console.info(msg)
      }
    }
  }
</script>

<style>
</style>
