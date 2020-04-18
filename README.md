# vue
## 利用方法
|  方法  |  利用方法  |
| ---- | ---- |
|  <script>で直書き  |  プロトタイプ、学習用  |
|  npm  |  実際の開発  |

## 基本的なvue
```
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
```
```
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: 'Learn JavaScript' },
      { text: 'Learn Vue' },
      { text: 'Build something awesome' }
    ]
  }
})
```
