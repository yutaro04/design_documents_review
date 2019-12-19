# テーブル定義書問題指摘
## 全体
- テーブル名の命名がNG（小文字だけになってない/スネークケースにじゃない/複数形じゃない）
- idというカラムがない（テーブル名_idとしなくていい）

## admins
- admin_idにindexがない。
- admin_email, admin_passwordとなっているが、テーブル名から判断できるのでadmin_の接頭辞はいらない。

## users
- user_l_name, user_f_name, user_l_kana, user_f_kana, user_telは略語を使っているので使わないように。
- member_statusだと、結局userの何のステータスを意味するかわからない。

## ships
- 主キーにindexがない
- ship_name, ship_address, ship_tel, ship_codeとなっているが, admin同様にship_の接頭辞はいらない。

## products
- stockは入荷と売上から算出できるので不要
- stock_statusは算出した在庫数から判別できるので不要。

## discs
- disc_numのdisc_は不要
- products_idはproduct_idにする。外部キーなので。

## songs
- songというカラム名から曲名だと判断できない

## labels
- labelというカラム名から名前だと判断できない

## artists
- artistというカラム名から名前だと判断できない

## genres
- genreというカラム名から名前だと判断できない。

## cart items
- テーブル名をcart_itemsにして、空白に_を挿入する
- products_idはproduct_idにする
- buy numは間を_でつなげる

## sell_details
- 購入時の価格を保持するカラムがない
- 親モデル(sell)のidをもっていない

## sell
- totalは何のtotalかわからない。
- 子モデルのidは不要

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
