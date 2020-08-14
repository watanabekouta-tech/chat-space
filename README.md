## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|unique: true,null: false|
|email|string|unique: true,null:false|
|pass|string|null: false|
### Association
- has_many  :groups,through: :groups_users
- has_many  :messages
- has_many  :groups_users

#1対1、1対多、多対多どれなのか


## グループテーブル

|Column|Type|Options|
|name|string|null: false|


### Association
- has_many :messages
- has_many  :users,through: :groups_users
- has_many :groups_users
#中間テーブルを利用する場合のアソシエーション表記



## メッセージテーブル

|Column|Type|Options|
|message|text||
|img|string||
|use_id|integer|null:false,foreign_key: true|
|group_id|integer|null:false,foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

#1対1、1対多、多対多どれなのか





## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|foreign_key: true,null: false|
|user_id|integer|foreign_key: true,null: false|

#インデックス、外部キー制約　optionを考える

### Association
- belongs_to:user
- belongs_to :group

#1対1の関係に書き直す










groups
messages
groups_users
それぞれのテーブルのカラムと、Type, Optionsを考えてみましょう。