---
title: 宣言
---

Svelteは、コンポーネントの状態が変化すると、DOMを自動的に更新します。しばしば、（例えば、*他の*部分から計算されるコンポーネントの状態の必要性の一部`fullname`に由来`firstname`と`lastname` ）、及びそれらが変化するたびに再計算。

これらについては、*リアクティブ宣言があり*ます。彼らはこのように見えます：

```js
let count = 0;
$: doubled = count * 2;
```

> これが少し異星人に見えても心配しないでください。これは[有効な](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label)（型にはまらない場合）JavaScriptであり、Svelteは「参照される値のいずれかが変更されるたびにこのコードを再実行する」ことを意味すると解釈します。一度慣れれば、後戻りはできません。

マークアップでdoubleを使用`doubled`ましょう：

```html
<p>{count} doubled is {doubled}</p>
```

もちろん、代わりにマークアップに`{count * 2}`と書くこともできます。リアクティブな値を使用する必要はありません。リアクティブ値は、それらを複数回参照する必要がある場合、または*他の*リアクティブ値に依存する値がある場合に特に価値があります。
