# correctCount
countアプリよくあるエラー問題集
ジャンル別

- code
    - association
    - pos
    - spel

- file
    - infinity
    - noImage

- storyboard
    - association
    - entryPoint
    - hidden
    - hierarchy
    - userInteractionEnabled
    - wh

- original

originalは元のファイル

## code
### 関連付け
難しめ
Storyboardのはじめの画面は、ViewControllerという名前と紐付けられている
名前が違うとコンパイルエラーは出ないが、はじめの画面が起動しない
クラス名をViewControllerにする

### pos
かっこがない
クラスのまとまり、関数のまとまり、を意識する
そのためのインデント

### spel
スペルミス

## file
### infinity
なぜかよくあるやつ。コピーしたいのにコピーが終わらない問題が発生する
プロジェクト内にプロジェクトフォルダをD&Dして、Copy If neededにチェックを入れずに、Create folder Referenceを選択してFinishしたら出来ました。
画像をD&Dするときに間違えてフォルダごとD&Dするのかなあ・・・

起こった後の対処はXcodeから無限の原因になってるフォルダ参照（青い方）のRemove Referenceすることです（対処不安な方は、このリポジトリをcloneして、file/infinity/countErrorから試せる）

### noImage
infinityの状態から復帰した時によくある
画像がないので、再度追加する必要があるが、リファレンスがないだけで実際のファイルはプロジェクトフォルダ内にあることも多い。


## storyboard
### association
### entryPoint
割とよくある。Main.storyboardやinitial view controllerを間違えて消してしまったあとに、追加したりするとこの状況起こりがち。
inspectorから、isInitialViewControllerのチェックを入れる

### hidden
パーツがhiddenになっている
inspectorから、hiddenのチェックを外す

### hierarchy
背景がボタンとかラベルを覆い隠してる。ボタンとかが見えなかったらほぼこれ。画像の都合で画像が真っ黒とかだと気づきにくいので注意。

Xcodeのバグで、正しい順でも表示がおかしくなることがあるが、これは一度ヒエラルキーを変えて、再び戻すことで対処できる。

### userInteractionEnabled
ボタンが押せなくなる現象
userInteractionEnabledのflagが何かしらでdisabledになっていると、ボタンが効かない
inspectorからenabledに戻す

### wh
起動してみると正しいのに、storyboardではおかしい。
storyboardの下、普段はw: Any, h: Anyになっているので、そのように戻す
storyboardと画面が一致しないならこれかも
