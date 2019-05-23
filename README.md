# text2pencentage

> 陈兴林 454674774@qq.com

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
    height="400"
    pencentage="0.5"
    fill="#ff1234"
    unit="M"
    text="106.5"
    unitColor="#ff3456"
></vue-text-pencentage>
```
