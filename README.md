# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,add_index|

## Association
has_many :group, through:members
has_many :members
has_many:messages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

## Association
has_many :user, through:members
has_many :members
has_many:messages

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## messegesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user