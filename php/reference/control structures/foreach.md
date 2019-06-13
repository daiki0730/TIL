## foreach
配列を反復処理するための便利な方法です。  
foreach が使えるのは配列とオブジェクトだけであり、 
別のデータ型や初期化前の変数に対して使うとエラーになります。  

- この構造には二種類の構文があります。 
  - foreach (array_expression as $value)  
  最初の形式は、array_expressionで指定した配列に 関してループ処理を行います。  
  各反復において現在の要素の値が $valueに代入され、内部配列ポインタが一つ前に 進められます。 
  (よって、次の反復では次の要素を見ることになります。) <br>
  
  - foreach (array_expression as $key => $value)
  2番目の形式は、さらに各反復で現在の要素のキーを変数 $keyに代入します。 
  
```

<?php
$arr = array(1, 2, 3, 4);
foreach ($arr as &$value) {
    $value = $value * 2; // $arr は array(2, 4, 6, 8) となります
}

unset($value); // 最後の要素への参照を解除します
?>

```

[PHP foreach](https://www.php.net/manual/ja/control-structures.foreach.php)
