## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|unique: true,null: false|
|email|string|unique: true,null:false|
|pass|string|null: false|
### Association
- has_many  :group,through: :groups_users
- has_many  :message

#1対1、1対多、多対多どれなのか



## グループテーブル

|Column|Type|Options|
|group_name|string|null: false|


### Association
- has_many :messages
- has_many  :users,through: :groups_users
- has_many :groups_users
#中間テーブルを利用する場合のアソシエーション表記



## メッセージテーブル

|Column|Type|Options|
|message|string|null: false|
|img|string||
| use| string| null:false|
| group| string| null:false|
### Association
- belongs_to :users
- belongs_to :groups
#1対1、1対多、多対多どれなのか





## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|string|null: false|
|user_id|string|null: false|
#インデックス、外部キー制約　optionを考える

### Association
- belongs_to:users
- belongs_to :groups
#1対1の関係に書き直す










groups
messages
groups_users
それぞれのテーブルのカラムと、Type, Optionsを考えてみましょう。