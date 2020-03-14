# テーブル設計

## userテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false unique: true|
|name|string|null: false|
|email|string|null: false, unique: true|

### Association
- has_many :groups, through :groups_users
- has_many :posts

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
|id|integer|null: false, unique: true|
|name|string|null: false|


### Association
- has_many :users, through :groups_users
- has_many :posts

## postsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|text|string|
|image|string|

### Association
- belongs_to :user
- belongs_to :group
