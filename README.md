# 目的
ハルナアウトラインの終了で失ったアウトライン編集体験を再取得する。

## ファイル自体の可搬性
- 操作対象は、構造化テキストファイル
- ディレクトリによるアウトライン管理ではない

## アプリ自体の可搬性
- TUIツールにて実現する

## 外部エディタの使用
- ユーザ設定の任意のエディタで編集できる

# 機能

## 外部エディタの呼び出し
- edit、microなどターミナルからコマンドラインで呼び出せるもの

## ツリー操作
- ノードの追加
- ノードの削除
- 配下ノードを含んだ削除
- ノードの移動
- 配下ノードを含んだ移動
- ノードの深さ変更
- 配下ノードを含んだ深さ変更

## マーク機能
- 完了チェックボックス
- 数種類のフラグ(任意の1文字、絵文字を使用することを想定)
- 下のノードをクリッピング

## 複製しない機能
- 文章の編集機能→ツリー操作のみ行うツールとする
- 複数の構造化テキストファイルへの対応
- 葉と枝の区別をしない(全てがタイトルを持った葉)
- ディレクトリでのツリー化
- 文字コード、改行コードの判定

# 機能詳細
## ファイルフォーマット
- 拡張子:.txt
- 文字コード:UTF8
- 改行コード:lf

## ノードタイトル
^\.{1,20}\t[^\t]{0,50}\t(.,){0,10}

### ノードシンボル
- 行頭「.」はノードタイトル
- 「.」の個数によってツリーの深さを示す。
- 最大20、ただし表示の保証はしない

### タイトル
- 制限について、未定。
- 空も許可するが、タブ文字は使用できない。

### オプション
最大10のフラグを設定できる。未定。

### ノードの区切りについて
「.」で始まる行から、次の「.」で始まる行の前の行まで。

### レベル判定
- 同じ高さのノードを自動で特別化したりはしない
- レベルは抜いて設定できる(レベル1の下にレベル10のノードが直接ぶら下がれる)

### 順序
判定しない。ファイル上の順行に従う。

## 性能
- 1ＭByteのファイルを、5秒以内にオープンできること。
