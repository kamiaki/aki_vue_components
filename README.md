# VUE组件库，欢迎使用😘

## 下载地址

```shell
npm install aki_vue_components
```



## 使用方法示例

```vue
全局引入
main.js
import akiVueComponents from 'aki_vue_components'
Vue.use(akiVueComponents)

按需引入
import {AkiButton1} from 'aki_vue_components'

<Aki-Button-1 style="width: 100px;height: 20px" @bClick="showmsg()">我是一个按钮</Aki-Button-1>
```



## 文档

### 1.按钮

```
Aki-Button-1
Aki-Button-2
Aki-Button-Left
Aki-Button-Right
Aki-Sidebar-Button-1
```

说明

```css
// 设置宽高
style="width: 100px;height: 20px"
```

| 属性名  | 参数说明 |
| ------- | -------- |
| @bClick | 点击方法 |

Aki-Sidebar-Button-1

| 属性名       | 参数说明                                                     |
| ------------ | ------------------------------------------------------------ |
| :circleStyle | 旋转的圆设置{width: '40px',height: '40px',bottom: '-15px',left: '-10px'} |



### 2. 开发中...