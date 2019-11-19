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

* ...

# DB設計
## usersテーブル
| Column    | Type   | Options    |
| user_name | string | null:false |
| email     | string | null:false |
| password  | steing | null:false |
### Association
- has_many :posts
- has_many :groups

# postsテーブル
| Column  | Type    | Options                     |
| body    | text    |                             |
| image   | string  |                             |
| user_id | integer | null:false,foreign_key:true |
### Association
- belongs_to :user

# groupsテーブル
| Column     | Type | Options |
| group_name | text |         |
### Association
- has_many :users

# users_groupsテーブル
| Column   | Type    | Option                      |
| user_id  | integer | null:false,foreign_key:true |
| group_id | integer | null:false,foreign_key:true |
### Association
- belongs_to :post
- belongs_to :user
