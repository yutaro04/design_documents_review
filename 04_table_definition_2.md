# テーブル定義書2
## 全体
- PKはidで大丈夫です。
- テーブル名の頭文字は大文字にしましょう。

## admins
- admin_idにindexがないです。
- email・passwordで大丈夫です。

## users
- カラム名に略語を使うのはやめましょう。
- email・passwordで大丈夫です。

## ships
- ship_idにindexをつけましょう。
- name・address・code・telで大丈夫です。

## products
- stockカラムは不要です。
- products_idではなくproduct_idです。

## discs
- disc_idにindexつけましょう。
- products_idではなくproduct_idにしましょう。
- disc_numカラムはどういった用途ですか？

## songs
- 曲名カラムはnameにしましょう。
- 曲順カラムを持たせましょう。

## genres
- ジャンル名カラムはnameなどとしましょう。

## labels
- レーベル名カラムはnameなどとしましょう。

## artists
- アーティスト名カラムはnameなどとしましょう。

## cart items
- buy numカラムはbuy_numカラムとアンダースコアをつけましょう。
- products_idではなくproduct_idです。
- Cart item_idではなくcart_item_idにしましょう。
- 小計金額カラムは必要ありません。

## sell details
- products_idではなくproduct_idにしましょう。
- product_idはFKを持たせましょう。
- FKとしてsell_idを渡しましょう。

## sells
- totalだけだと何のトータルかがわかりません。
- FKにsell_details_idは必要ありません。
- payカラムだけだとそれがどんなカラムわからないので一目でカラムの意味がわかるようなカラム名にしましょう。


# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
