## メモ
> TensorFlow JSをより分かりやすくしたライブラリ
- https://ml5js.org/
* これを使うとモデルを指定するだけで、学習可能。
JavaScriptのコード
~~~ 
//MobileNetをここで指定する。
ml5.imageClassifier('MobileNet') 
    //id指定して取得した画像を代入
  .then(classifier => classifier.classify(image)) 
  .then(results => {
    
    result.innerText = results[0].label;
    probability.innerText = (results[0].confidence * 100).toFixed(2);

    results.forEach(element => {
      //他の予測したものをコンソール表示
      anotherans.append("予想:" + element.label
         + "確率:" + (element.confidence * 100).toFixed(2) + "%");
      anotherans.append(document.createElement("br"));
    });
});
~~~
以上のように簡単に機械学習アプリを作ることができる。

# TensorFlow JS
- その名の通りTensorFlowをJSで実装したもの  
これを使えばかなり軽量にAIを搭載したシステムを作成することが可能
- 今までに作成したモデルをコンバーターで変換すると、すぐに利用可能