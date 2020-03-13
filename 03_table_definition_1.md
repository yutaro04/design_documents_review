# テーブル定義書1
## 全体
-テーブル名の命名規則が間違っております。
-idがありません。（PKはidで大丈夫です）
-カラム名にテーブル名をつける必要はありません。
-created_at,updated_atが全てユーザー登録・更新日時になっています。

## admin
- テーブル名をadminsにしましょう。
- PKがありません。

## users
- カラム名に略ごを使うのはやめましょう。
-郵便番号・電話番号のデータ型はintegerではなくstringにしましょう。

## products
- disc_id・artist_id・genre_id・label_idにFKを持たせましょう。

## discs
- products_idではなくproduct_idにしましょう。
-discが複数あることを考慮しましょう。

## songs
- 曲名カラムのデータ型はintegerではなくstringにしましょう。
-曲順カラムを持たせましょう。

## labels
- product_idは不要です。
-labelカラムはlabel_nameなどと一目でカラムの意味がわかるようなカラム名に変更しましょう。

## artists
- product_idは不要です。
-artistカラムはartist_nameなどと一目でカラムの意味がわかるようなカラム名に変更しましょう。

## genre
-product_idは不要です。
-genreカラムはgenre_nameなどと一目でカラムの意味がわかるようなカラム名に変更しましょう。


## cart item
-products_idではなくproduct_idにしましょう。
-buy numカラムはbuy_numカラムとアンダースコアをつけましょう。
-小計金額カラムは必要ありません。

## buy　details
-buy numカラムはbuy_numカラムとアンダースコアをつけましょう。

## buy
-buy_details_idは必要ありません。
-payカラムだけだとそれがどんなカラムわからないので一目でカラムの意味がわかるようなカラム名にしましょう。
-支払い方法はenumを考慮しデータ型を変えましょう。
-郵便番号がありません。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
