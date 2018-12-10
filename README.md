# CSS utils
[![npm](https://img.shields.io/npm/v/@lucky-joel/css-utils.svg) ![npm](https://img.shields.io/npm/dm/@lucky-joel/css-utils.svg)](https://www.npmjs.com/package/@lucky-joel/css-utils)
[![Open Source Love](https://badges.frapsoft.com/os/mit/mit.svg?v=102)](https://github.com/ellerbrock/open-source-badge/)

常用 CSS 工具类。快速做页面，少写重复代码，减少起类命的痛苦。

## 安装
```
npm install @lucky-joel/css-utils --save
```

或用 CDN
```
<link rel="stylesheet" href="https://unpkg.com/@lucky-joel/css-utils" />
```


## 使用
<details>
  <summary>详细</summary>

普通项目
```
<link rel="stylesheet" href="path-to/node_modules/css-utils-collection/dist/min/index.css" />
```

未压缩版
```
<link rel="stylesheet" href="path-to/node_modules/css-utils-collection/dist/index.css" />
```

webpack 项目
```
<style src="css-utils-collection"></style>
```

注意，需要安装了 style-loader。
</details>


## Demo
* [常见布局](https://iamjoel.github.io/css-utils-collection/example/layout)
* [仿掘金](https://iamjoel.github.io/css-utils-collection/example/juejin)
* [仿微信的信息列表](https://iamjoel.github.io/css-utils-collection/example/list)

## 说明
<details>
  <summary>用 CSS 工具类做页面的优缺点</summary>
在做页面的过程中，给元素添加样式，常规做法是给元素加个类名。起个合适的类名，还满难的。如果我们把常用的样式定义成一个个工具类名，那么很多情况，我们只需要在元素上加工具类名，而不需要专门取名字。例如，做一个图文的列表，我们以前可能会这么写：

```
<div class="list">
  <div class="media">
      <img src="http://via.placeholder.com/50x50" class="media__img" />
      <div class="media__body">
        <div class="media__line">
          <div class="media__title">标题</div>
          <div class="media__time">2017/12/10</div>
        </div>
        <div class="media__summary">摘要</div>
      </div>
    </div>

    <div class="media">
      <img src="http://via.placeholder.com/50x50" class="media__img" />
      <div class="media__body">
        <div class="media__line">
          <div class="media__title">标题</div>
          <div class="media__time">2017/12/10</div>
        </div>
        <div class="media__summary">摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长</div>
      </div>
    </div>
</div>
```

用工具类名的方式，这么写：
```
<div>
  <div class="ly bb p-10">
      <img src="http://via.placeholder.com/50x50" class="br-sm mr-10" />
      <div class="lyi-fill">
        <div class="mb-10 ly ly-justify">
          <div class="fz-lg">标题</div>
          <div class="fz-sm c-grey">2017/12/10</div>
        </div>
        <div class="t-ddd">摘要</div>
      </div>
    </div>

    <div class="ly bb p-10">
      <img src="http://via.placeholder.com/50x50" class="br-sm mr-10" />
      <div class="lyi-fill">
        <div class="mb-10 ly ly-justify">
          <div class="fz-lg">标题</div>
          <div class="fz-sm c-grey">2017/12/10</div>
        </div>
        <div class="t-ddd">摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长摘要很长很长</div>
      </div>
    </div>
</div>
```

这样写的优点：
* 减少起类名的次数。从而提高做页面的速度。
* 写好类名后，样式基本已满足要求了。减少总的 CSS 代码量。

缺点：
* 一个元素可能会用很多个类名,代码上有点丑。

注意：这种写法适用写不可复用的页面。写组件，还是用给元素加类名的方式比较好。
</details>

## 支持的工具类
<details>
  <summary>详细</summary>
从外而内，从垂直（上到下）到水平（左到右），从布局(大小)到细节（颜色，字的粗细）。包括：

* position,z-index,top,bottom,left,right。工具类:
  * `pos-r`
* margin。工具类:
  * `m[t|b|l|r|v|h]-<0|5|10|15|20>[rem]`
* 盒模型。工具类:
  * `border-box`, `content-box`
* border。工具类:
  * `b[t|b|l|r|v|h]`
* border-radius 圆角
  * `br-<lg|md|sm|round>`
* cursor 鼠标
  * `cursor-p` 手形
  * `cursor-na` 禁用
* padding。工具类:
  * `p[t|b|l|r|v|h]-<0|5|10|15|20>[rem]`
* background。工具类:
  * `bgc-grey`
  * `bgz-<cover|contain|100per>`
* display。 flex,block...
  * `ly`
  * `d-<b|ib|n>`
  * `v-h`: `visibility: hidden`
* height。工具类:
  * `h-100per`: height: 100%
* flex-direction
  * `lyd-c`: 对应 `flex-direction: column`
* flex-wrap
  * `ly-multi` 多行
* align-items, align-self 垂直对齐
  * `ly-<t|m|b>`
* line-height
  * `lh-<lg|md|sm>`
* width
  * `w-50,w-100` : 对应 `width: 50%,width: 100%`
* flex-grow
  * `lyi-fill`
* justify-content 水平对齐
  * `ly-<j|c|a|r>`
* text-align 文本水平对齐
  * `ta-<c|r>`
* text
  * `t-ddd` :单行文本超出加省略号。
  * `t-ly-j` :文字两端对齐。
  * `t-no-select`：禁止选择文本。
  * `tt-u`：字母大写。
* font
  * `fz-<xl|20|lg|18|md|16|sm|14|xs|12>` xl,lg,md,sm,xs 分别对应 20px, 18px, 16px, 14px, 12px。
  * `fw-<b|l>`
  * `ff-<yahei|hei|song>`
  * `c-<i|white|black|000|333|666|999|grey|light-grey|primary>` 。`c-i` -> `color: inherit`
* 复合规则
  * `ly-abs-c`: 宽度不固定的绝对定位元素水平居中
  * `ly-abs-m`: 高度不固定的绝对定位元素垂直居中
  * `placeholder` 来做组件占位。
  * `img-rwd` 响应式图片
* 兼容性的
  * `smooth-scroll` 解决 当内容很多时，ios 的滚动比较生涩 的问题。
* 其他：这些需要引用额外的css。在 `dist/more` 下
  * `triangle-<t|r|b|l>` 实心三角。

</details>

更多见[源码](./src/index.scss)。

## 约定
<details>
  <summary>详细</summary>

* 类名规则是`样式单词的首字母缩写-值`。如
  * `mb-10` -> `margin-bottom: 10px`
  * `ta-c` -> `text-align: center`
  * 特例
    * `ly` 布局相关相关的。
    * `pos` -> `position`， border-box, content-box。 
* xl, lg, md, sm, xm 分别代表 特大，大，中等，小，特小。
* t,r,b,l,v,h 分别表示上，右，下，左，垂直，水平。
* 默认数值的单位是px，如 `mb-10` -> `margin-bottom: 10px`。 百分比的单位是 `per`: 如，`w-100per` -> `width: 100%;`。rem 的单位是rem：如 `pr-10rem`。
* 颜色深浅，分别用 dark，light。如
  * `c-light-grey`
* 类名的值采用 [BNF](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form)(巴科斯范式)。常见符号的意义，如下
  * `<>`: 必选项。
  * `[]` : 可选项。
  * `{}`: 内包含的为可重复0至无数次的项。
  * `|`: 分隔不同选项。
* 要增加优先级，可以在类名后面加`-i`。该样式会加被加上 `!important`。 如 `ta-c-i`。
</details>
