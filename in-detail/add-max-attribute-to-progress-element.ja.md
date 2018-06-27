# `progress`要素には`max`属性を追加する

`max`属性があると、`value`属性を簡単な形式で書けます。

悪い例:

    <progress value="0.5"> 50%</progress>

良い例:

    <progress max="100" value="50"> 50%</progress>


## 解説

HTML5で新設された`progress`や`meter`要素は経過や蓄積を表現する要素です。どれくらい過ぎたかや溜まったかは`value`属性を使って表現します。その`value`属性では0から1の間で指定するのですが、`min`属性や*特に`max`属性*を指定しておくことでその範囲を変更できます。

悪い例では「50%進んでいる」ことを表現するのに`0.5`を指定しています。対して良い例で挙げたように`max`属性`100`を指定しておくと、`50`で「50%」を表現できます。どちらがわかりやすいかは明白でしょう。

このことは`progress`や`meter`要素をJavaScriptで操作する時にもメリットがあります。悪い例で挙げたように`max`属性がないと、`value`属性の値と中身のために、数字を整形するコードを書き分けなければなりません。良い例で挙げたように両者を同じ数字で扱えるようにしておけば、より簡潔にコードが書けるはずです。