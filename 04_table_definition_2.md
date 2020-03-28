# テーブル定義書2
## 全体
- admin_id, user_idなどとせず、単にidなどでよい
- user_tel, user_passwordなども同様

## admins
- 

## users
- user_l_nameなどと省略しないほうが良い
- user_l_nameの備考に”名前”は不適当
- zip_codeだと機能がわかりにくい
- member_statusだと機能がわかりにくい
- member_statusのデータ型がintegerとなっているにも関わらず、DEFAULTがFALSEはおかしい
- member_statusのデータ型にenumは違和感がある。備考に書きたい

## ships
- ship_nameだと機能がわかりにくい。

## products
- products_idと複数形になってるいるが、不適切
- image_idにNOT NULL属性は不要
- image_idのDEFAULTとして"画像準備中"は不適切
- cd_titleだと機能が不明瞭
- ディスクの枚数を表すカラムが必要
- disc_numなどと省略形を使わないほうがいい

## discs
- products_idと複数形になっているが、不適当

## songs
- カラム名songだとわかりにくい。

## labels
- カラム名がlabelだとわかりにくい。

## artists
- カラム名がartistだとわかりにくい

## genres
- カラム名はgenreだとわかりにくい

## cart_items
- カラム名がCart_item_idと大文字になっているのは不適当
- products_idと複数形になっているのは不適当
- まだ購入しているわけではないのでbuy_num、購入枚数は不適当

## order_details
- products_idと複数形になっているのは不適当
- product_idはFKに指定する

## orders
- カラム名としてpayだとわかりにくい
- ship_codeだとわかりにくい
- ship_nameだとわかりにくい
- ship_costだとわかりにくい
- 単にtotalだとなんの合計かわかりにくい

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
