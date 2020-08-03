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
|title|text|null: false|
|text|text|null: false|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- has_many :comments
- has_many :posts_tags
- has_many  :tags,  through:  :posts_tags

## chat_membersテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|

### Association
- has_many :chat_members
- has_many  :posts,  through:  :chat_members