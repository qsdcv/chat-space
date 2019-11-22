## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
### Association
- has_many :groups
- has_many :talks
## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|username|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :grops
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
## chatsテーブル
|Column|Type|Options|
|------|----|-------|
|talk|text||
|image|text||
|user_id|integer|null: false, foreign_key: true|
|username|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|groupname|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
- has_many :talks
## group_chatテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|chat_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :chat
## talkテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|chat_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
- belongs_to :chat
