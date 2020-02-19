## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


### userテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|

### Association
- has_many :messages
- hans_many :user_groups


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|id|interger|null: false, primary_key|
|body|text|null: false|
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|interger|null: false, primary_key|
|nickname|string|null: false|

### Association
- has_many :messages
- has_many :user_groups