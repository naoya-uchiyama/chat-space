# README

# chat_space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unipue: true|
|email|string|null: false, unipue: true|
|password|string|null: false|
### Association
- has_many :groups, through:  :groups_users
- has_many :messages
- has_many :groups_users


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many  :users, through:  : groups_users
- has_many  :messages
- has_many  :group_users

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
-belongs_to :user
-belongs_to :group
