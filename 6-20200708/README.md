## 响应式布局用到的技术，移动端需要注意什么

vw+vh+rem

1.vw、vh 是基于视口的布局方案，故这个 meta 元素的视口必须声明。（解决宽高自动适配）

```javascript
 <meta name="viewport" content="width=device-width,initial-scale=1.0">
```

2.rem 布局-解决字体适配
rem 布局原理：根据 CSS 的媒体查询功能，更改 html 根字体大小，实现字体大小随屏幕尺寸变化。

```javascrpit
  @media only screen and (max-width: 1600px) and (min-width: 1280px){
    html{
      font-size: 14px;
    }
  }
  @media only screen and (max-width: 1280px) and (min-width: 960px){
    html{
      font-size: 12px;
    }
  }
  @media only screen and (max-width: 960px){
    html{
      font-size: 10px;
    }
  }
```

3、vw、vh、rem 的使用

在移动端 web 开发中，UI 设计稿中设置边框为 1 像素，前端在开发过程中如果出现 border:1px，测试会发现在某些机型上，1px 会比较粗，即是较经典的 移动端 1px 像素问题。
设备的 物理像素[设备像素]和逻辑像素[CSS 像素]
可以使用 viewport + rem 或者 transform: scale(0.5)来实现
