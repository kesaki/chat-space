# テーブル設計

## userテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|name|string|null: false|

### Association
_ has_many groups, through: groups_users
_ has_many posts

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null:false, foreign_key: true|
|name|string|null: false|


### Association
- has_many :users, through: groups_users
- has-many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|text|string|null: true|
|url|string|null: true|

### Association
belongs_to user
belongs_to group
