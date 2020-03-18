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


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
|first_name|string|null: false|
|last_name|string|null: false|
|first_name_kana|string|null: false|
|last_name_kana|string|null: false|
|birth_date|date|null: false|
|tel|integer|null: false, unique: true|
### Association
- has_many :Exhibitions
- has_many :comments
- has_many :pays


## Exhibitionsテーブル 
|Column|Type|Options|
|------|----|-------|
|image|text|null: false|
|product_name|string|null: false|
|product_version|text|null: false|
|category1|string|null: false|
|category2|string||
|category3|string||
|brand|string||
|product_condition|string|null: false|
|delivery_select|string|null: false|
|delivery_method_include_fee|string|null: false|
|delivery_method_COD|string|null: false|
|suppliev_region|string|null: false|
|delivery_date|string|null: false|
|price|integer||
|user_id|integer|null: false, foreign_key: true|
|saler_id|integer||
|buyer_id|integer||
### Association
- belongs_to :user
- has_many :comments


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|Exhibition_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :Exhibition


## paysテーブル
|Column|Type|Options|
|------|----|-------|
|card_nunber|integer|null: false|
|month|integer|null: false|
|day|integer|null: false|
|security_code|integer|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user





