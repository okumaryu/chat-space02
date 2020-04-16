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

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false, unique:true|
|id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
-has_many :users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index:true,null: false, unique:true|
|mail|string|null: false, unique: true|
|id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
-has_many :groups, through:members
-has_many :messages
-has_many :members

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
|user-id|integer|null: false, foreign_key: true|
|id|integer|null: false|
