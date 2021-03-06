# vue-img-cutter
> vue图片裁剪插件，支持任意尺寸裁剪，限制比例裁剪，拖动，缩放
> 兼容IE8+,MSEdge,Chrome,Firefox

![插件截图](http://www.ihtmlcss.com/wp-content/uploads/2019/06/img-cutter.png)

##### 演示地址：[http://ihtmlcss.com/demo/dist/#/croptool](http://ihtmlcss.com/demo/dist/#/croptool)
##### 项目地址：[https://github.com/acccccccb/vue-img-cutter](https://github.com/acccccccb/vue-img-cutter)

### 使用方法

```
npm install vue-img-cutter --save-dev
```
> 1. 将ImgCutter.vue文件引入项目：
```
import ImgCutter from 'vue-img-cutter'
export default {
        components:{
            ImgCutter
        },
...
}
```
> 2. 在template中使用：

```
<ImgCutter
    :label="'选择图片'"
    :boxWidth="700"
    :boxHeight="400"
    :cutWidth="250"
    :cutHeight="250"
    :rate="'1:1'"
    :sizeChange="true"
    :moveAble="true"
    v-on:cutDown="cutDown">
    <button slot="open">选择图片</button>
</ImgCutter>
```

### 参数说明：

| 属性名 | 作用 | 类型  | 必填 | 默认值 |
|:----:|----|:----:|:----:|:----:|
|label|默认打开裁剪工具按钮的显示文字|String|否|选择图片|
|boxWidth|裁剪工具宽度|Number|否|800|
|boxHeight|裁剪工具高度|Number|否|400|
|cutWidth|默认裁剪宽度|Number|否|200|
|cutHeight|默认裁剪高度|Number|否|200|
|tool|是否显示工具栏|Boolean|否|true|
|sizeChange|是否能够调整裁剪框大小|Boolean|否|true|
|moveAble|能否调整裁剪区域位置|Boolean|否|true|
|rate|图片比例|String(例: "4:3")|否|-|
|cutDown|完成截图后要执行的方法|Function|是|-|
> 支持slot，在组件内部使用带有slot="open"属性的元素即可自定义打开组件的按钮

### 返回值：
| 属性名 | 类型  |
|:----:|:----:|
|fileName|文件名|
|file|file类型的文件对象|
|blob|blob类型的文件对象|
|dataURL|dataURL|

### 更新日志 
#### 2.0.21
- 兼容IE8+,MSEdge,chrome,firefox
- 新增了设置参数，可固定裁剪框位置，固定裁剪尺寸，具体请看参数说明
- 修复了非IE系浏览器不返回file对象的问题
#### 2.0.20
- 兼容IE11+,MSEdge。IE11以下版本未测试

#### 2.0.19
- 修改了返回值，现在将追加返回文件名和file类型的文件对象

#### 2.0.18

- 修复了点击选择图片按钮时有一定几率刷新页面的问题

#### 2.0.17

- 调整了样式
- 修正了弹窗超出屏幕后被遮挡的问题

#### 2.0.16

- 修正了旋转工具条显示错误的问题

#### 2.0.15

- 增加工具栏 可对图片进行旋转/缩放操作
- 优化了动画效果
