# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
|created_at|integer|null: false, foreign_key: true|
|updated_at|integer|null: false, foreign_key: true|

#### Association
- has_many :groups
- has_many :users
- has_many :chats

#### chatsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|text|text|null: false, foreign_key: true|
|image|text|null: false, foreign_key: true|
|created_at|integer|null: false, foreign_key: true|
|updated_at|integer|null: false, foreign_key: true|

##### Association
- belongs_to :user
