# テーブル定義書1
## 全体
- railsの命名規則に則って無い

- 全テーブルのPKにおいて、AUTO_INCREMENT、INDEXはデフォルトで◯が入ってる

- PKに◯が一つも入って無いところが多数

## Users
- 郵便番号、電話番号のデータ型は適して無い

- 名前（名、名カナ）のNOT NULLに◯がない

## Products
- 本来FKに◯が必要なところに◯が入っていない

- ジャケットのデータ型が違う

- cd_imageがrefileを使っている場合、_idの追記が必要

## Songs
- 曲名がinteger、カラム名song_nameとかの方がいい

## Labels
- カラム名labelをlabel_nameとかにした方がいい

## Artists
- アーティスト名がinteger、カラム名artist_nameとかの方がいい

## Genre
- ジャンル名がinteger、カラム名genre_nameとかの方がいい

## Cart item
- products_idにデータ型がない

## Buy
- 購入日は必要でない

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

