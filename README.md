# Datebase Design
## users table
|Column|Type|Options|
|------|----|-------| 
|name|string|null:false|
|password|string|null:false|
|email|string|null:false|

### Association
- has_many :users_groups
- has_many :groups, through: : users_groups
- has_many :messages

## groups table
|Column|Type|Options|
|------|----|-------|
|name|string|null:false|

### Association
- has_many :users_groups
- has_many :users, through: :users_groups
- has_many :messages

## users_groups table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false, foreign_key:true|
|group_id|integer|null:false, foreign_key:true|

### Association
- belong_to:user
- belong_to:group

## messages table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false, foreign_key:true|
|group_id|integer|null:false, foreign_key:true|
|post_date|datetime||
|text|text||
|image|string||

### Association
- belong_to:user
- belong_to:group

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
