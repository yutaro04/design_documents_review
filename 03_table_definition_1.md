##テーブル定義書1

#全体
- idのカラム名は~_idではなく、単にidでよい
- 配送先テーブルが必要
- 入荷テーブルが必要

#Admin
- テーブル名は複数形とする
- idをPKとする必要がある
- admin_email, admin_passwordは単にemail, passwordでよい
- 
#Users
- テーブル名はend_usersテーブルなどとすほうがよい
- カラム名にuser_l_nameなどと略語を使わないほうがよい
- user_l_name, user_l_kana, user_telなど、userを付ける必要はない
- user_f_name, user_f_kanaにもNOT NULL制約を付与する
- user_l_nameの備考として”名前”は端的すぎるし、不要
- zip_codeはpostal_codeなどとしたほうがよい
- zip_code, telカラムのデータ型はstringとする。（0から始まる場合があるため）。備考も削除する
- 配送先テーブルがあるため、ship_addressカラムは不要
- member_statusカラムの名称がわかりにくいため、is_availableなどとし、データ型をboolean型としたい

#Products
- テーブル名はproducsよりもitemsなどとするほうが適切
- genre_id, label_id,artist_idをFKに指定する
- cd_image, cd_titileは単にimage, titleでよい
- imageにDEFAULTとしてnullを指定する必要はない
- imageカラムのデータ型はstringが望ましい
- 商品の販売ステータス（販売中か販売停止中か）を示すカラムがほしい
- ディスクの枚数を示すカラムが必要

#Discs
- products_idカラムでproductsと複数形になっているのは不適切
- 収録されている曲数や合計時間を示すカラムがほしい
#Songs
- 名前を示すカラム名はsongではなくnameが適当
- ↑のデータ型はintegerではなくstring

#Labels
- PKとしてidが必要
- label名を示すカラムとしてはlabelではなくnameが適当

#Artists
- PKとしてidが必要
- アーティスト名を示すカラムとしては、artistではなくnameなどが適当
- ↑のデータ型はintegerではなくstring

#Genre
- テーブル名はGenresとしたい
- ジャンル名を示すカラムとしてはgenreではなくnameなどが適当
- ↑のデータ型はintegerではなくstring
- ジャンルの有効無効を示すカラムがあるとよい

#Cart item
- テーブル名はCart_itemsと複数形にする
- PKとしてidが必要
- products_idではなく、単数形のproduct_id。データ型はinteger
- 購入枚数buy_numはすでに購入しているわけではないので単に数量amountなどとするほうがよい。
- 

#Buy details
- テーブル名は管理者側から見てorder_detailsなどとするほうが適切
- buy_numはわかりにくいため、単にamountなどとしたい。
- 購入id(buy_id)のデータ型はinteger、not null制約も付与

#Buy
- テーブル名は複数形にする
- payだとわかりにくい。（支払い方法は名詞系のpaymentとするのが適切）
- 支払い方法を表すカラムのデータ型はinteger型にする
- テーブル名は管理者側から見てordersなどとするほうが適切
- 注文状況（配送済、振込済みなど）を表すカラムが必要
- ship_addressなどは単にaddressなどとしてよい
- 支払合計は商品合計としたほうが良い（送料カラムがあるため）



# 指摘事項
## users
- user_l_name, user_l_kana, user_telなどは単にl_name, l_kana, tellでよい
 - l_nameなどの略語を使用するのはふさわしく無い
- member_statusカラムのデータ型をboolean型とした
  - どう言う意味ですか。。。
  - member_statusが何を意味してるカラムかわからないのでカラム名としてよくない
  
## products
- 商品のステータスを示すカラムがほしい
  - これはどういうことでしょうか
 

## discs
- ディスクの順番を表すカラムは要件にないため不要
  - こちらは必要です。
- あと２つ抜けているので考えてみてください！

## songs
- FKとしてディスクidカラムが必要
  - 存在してた気がする

## products
- FKとして商品id(product_id)を加えたい
  - これはいらないです
- priceカラムは不要。他のテーブルから導出できる。
  - priceカラムは持っておきましょう
- あと１つ指摘できることがあります

## buy
- 注文ステータスを示すカラムが必要
  - 注文ステータスとは
- 支払い方法は名詞系のpaymentとするのが適切
  - paymentとするのが適切では無いが、今回は問題指摘だけなので「payだと何を意味しているかわからない」程度にしておきましょう。


