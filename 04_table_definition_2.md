# テーブル定義書2
## 全体
- 各テーブルのPKのidの前に不要なモデル名がついている。

## admins
- PKにINDEXがない。
- emailとpasswordの前にadminがついている。

## users
- nameとkanaの前に不要なuser_〇がついている。
- emailとpasswordの前に不要なuserがついている。

## ships
- PKにINDEXがない。
- name,address,tel,codeの前のshipがついている。

## products
- 在庫数,在庫ステータスカラムがある。

## discs
- PKにINDEXがない。
- 外部キーがproducts_idになっている。
- nummの前に不要なdiscがついている。

## cart items
- テーブル名がスネークケースになっていない。
- PKにINDEXがない。
- 外部キーがproducts_idになっている。
- buy numはスペースが入っていてカラム名として使用できない。

## sell_details
- 外部キーがproducts_idになっている。
- 外部キーであるsell_idがない。
- 購入時の価格を保存するカラムがない。

## sells
- PKにINDEXがない。
- 購入詳細IDは不要。



