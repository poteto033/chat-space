# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation
# chat-space DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unique: true|
|password|string|null: false|
|username|string|null: false, unique: true|
### Association
- has_many :messages
- has_many :users_groups
- has_many  :groups,  through:  :users_groups

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body_id|integer|null: false, foreign_key: true|
|image_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :body
- belongs_to :image
- belongs_to :user
- belongs_to ;group

## bodiesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
### Association
- has_many :messages

## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|string|null: false|
### Association
- has_many :messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
### Association
- has_many :messages
- has_many :users_groups
- has_many :users, through:  :users_groups

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
