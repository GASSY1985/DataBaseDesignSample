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

## DB設計
### groups_users_table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

Association
- belongs_to :group
- belongs_to :user

#### users_table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|user_name|text|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
|created_at|timestamp|null: false, foreign_key: true|
|updated_at|timestamp|null: false, foreign_key: true|

Association
- has_many :chats
- has_many :groups
- has_many :groups, through: :groups_users_table

##### chats_table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|comment|text|null: false, foreign_key: true|
|image|text|null: false, foreign_key: true|
|created_at|timestamp|null: false, foreign_key: true|
|updated_at|timestamp|null: false, foreign_key: true|

Association
- belongs_to :user
- belongs_to :group

###### groups_table
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|group_name|text|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|created_at|timestamp|null: false, foreign_key: true|
|updated_at|timestamp|null: false, foreign_key: true|

Association
- has_many :chats
- has_many :users
- has_many :users, through: :groups_users_table
