## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|unique: true,null: false|
|email|string|unique: true,null:false|
|pass|string|null: false|
### Association
- has_many  :group,through: :groups_users
- has_many  :message
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
|message|string||
|img|string||
|use|string|null:false|
|group|string|null:false|
### Association
- belongs_to :user
- belongs_to :group

#1対1、1対多、多対多どれなのか





## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|string|foreign_key: true|
|user_id|string|foreign_key: true|

#インデックス、外部キー制約　optionを考える

### Association
- belongs_to:user
- belongs_to :group

#1対1の関係に書き直す










groups
messages
groups_users
それぞれのテーブルのカラムと、Type, Optionsを考えてみましょう。