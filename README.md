# text2pencentage

> 陈兴林 454674774@qq.com

## 描述

```bash
# 实现文本信息，根据父级宽度自动改变所占百分比
# 当宽度足够宽时，文字所占的百分比将是高度的百分比
# 同理，当高度足够高时，文字所占的百分比将是宽度的百分比
# 使用时，但当宽高合理是，内容将达到合理的百分比，使用者可以自由选择百分比朝向
```

## 下载

``` bash
# install
npm install text2pencentage -D
```

#### props

```bash
1. height 字符串类型，svg的高度，默认400px，只支持px单位
2. wdith 字符串类型，svg宽度，默认 auto
3. text 字符串类型，svg所要展示的文本内容，默认：test text
4. fill 字符串类型，svg所要展示的文本内容的字体颜色，默认：'#333'
5. unit 字符串类型，文本修饰符，例如展示某个数值的单位
6. unitColor 字符串类型，文本修饰符的字体颜色，默认: '#123456'
7. percentage 字符串 或 数值 类型，字体相对于父级的百分比，默认：100%
8. id 字符串类型，svg所在的父级，递归调用时，此id不可重复，默认：'text2pencentage'
```

#### 使用示例

main.js

```js
import text2pencentage from 'text2pencentage';
Vue.component('vue-text-pencentage', text2pencentage);
// 或
Vue.use(text2pencentage);
```

组件

```html
<vue-text-pencentage
  text="106.5"
  fill="#ff1234"
  percentage="0.8"
></vue-text-pencentage>
```

#### 效果图

![效果图](/src/assets/20190523001.png)


##### 可以把文字按百分比缩放，有兴趣的小伙伴可以 start 一下，初次写组件。不足的地方，望指正，感谢您的支持。
