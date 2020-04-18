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

## コンポーネントによる構成
 - すべてのタイプのインターフェイスはコンポーネントツリーとして抽象化することができる
 - dataにしてしまうと同じデータになってしまう。なので、プロパティに値を渡して、受け取れるようにする
```
<div id="app-7">
  <ol>
    <!-- 
      各 todo-item の内容を表す todo オブジェクトを与えます。
      これにより内容は動的に変化します。
      また後述する "key" を各コンポーネントに提供する必要があります。
    -->
    <todo-item
      v-for="item in groceryList"
      v-bind:todo="item"
      v-bind:key="item.id"
    ></todo-item>
  </ol>
</div>
```
```
Vue.component('todo-item', {
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})

var app7 = new Vue({
  el: '#app-7',
  data: {
    groceryList: [
      { id: 0, text: 'Vegetables' },
      { id: 1, text: 'Cheese' },
      { id: 2, text: 'Whatever else humans are supposed to eat' }
    ]
  }
})
```

# Vueインスタンス
## データ
[オプション-データ|https://jp.vuejs.org/v2/api/#%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3-%E3%83%87%E3%83%BC%E3%82%BF]
|  オプション  |  目的  |　型　|
| ---- | ---- | ---- |
|  data  |  データオブジェクト  |Object・Function　|
|  props  |  親コンポーネントからデータを受け取るためにエクスポートされた属性のリスト/ハッシュ  |Object・Array<string> <br>type [String, Number, Boolean, Array, Object, Date, Function, Symbol, カスタムコンストラクタ関数、またはそれらの配列]　<br>default: any プロパティのデフォルト値　<br>required: Boolean　プロパティが必須かどうか　<br> validator: Function プロパティの値を唯一の引数として受け取る、カスタムのバリデーション関数 |
|  computed  |  動的な算出プロパティ  |{ [key: string]: Function | { get: Function, set: Function } }　|
|  methods  |  Vue インスタンスに組み込まれるメソッド  |{ [key: string]: Function }　<br> ※アロー関数を使用すべきではないことに注意|
|  watch  |  キーが監視する評価式で、値が対応するコールバックをもつオブジェクト  |{ [key: string]: string | Function | Object | Array}|

## 
