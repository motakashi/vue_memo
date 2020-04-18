# vue
## 利用方法
|  方法  |  利用方法  |
| ---- | ---- |
|  <script>で直書き  |  プロトタイプ、学習用  |
|  npm  |  実際の開発  |

## 基本的なvue
```
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">Reverse Message</button>
</div>
```
|  書式  |  挙動  |
| ---- | ---- |
|  v-bind:  |  表示のバインディング  |
|  v-if=  |  条件分岐  |
|  v-for=  |  for文  |
|  v-on:click=  |  イベントリスナを加え、Vue インスタンスのメソッドを呼び出す  |
|  v-model=  |  双方向バインディング型　|

```
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: 'Hello Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```
|  書式  |  挙動  |
| ---- | ---- |
|　el  |  DOM構造のエレメント指定  |
|  data  |  初期の値  |
|  methods  |  呼び出されるメソッド  |

