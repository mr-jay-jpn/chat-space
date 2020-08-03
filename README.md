## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|
|image｜string｜
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :posts
- has_many :groups_users
- has_many :groups, through: :groups_users


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|unique: true|


### Association
- has_many :posts
- has_many :groups_users
- has_many :users, through: :groups_users


