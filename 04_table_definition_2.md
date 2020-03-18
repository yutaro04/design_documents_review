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
保持する* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

**研修担当レビュー**
<font color="Red">再提出の際はこのレビューを残しておいてください。</font>

## 全体
- テーブル名の頭文字は小文字が適切です。また、スネークケースで記述しましょう。

## users
- 「member_status」だと、何のステータスを表しているのかが伝わりません

## products
- stock_statusは算出した在庫数から判別できるので不要です。

## discs
- disc_numは、複数枚のディスクそれぞれに番号を与える役目があると思います。また「disc_num」よりも「num」の方が良いです。

## songs
- 曲順カラムは「track_num」があるため、追加する必要はないです！

## cart items
- 小計金額カラムは元から存在していません。(テシンくんの方に存在してたらごめんなさい)

## sell details
- 購入時の価格を保持するカラムがありません。
