## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

dd
### usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|

### Association
- has_many :messages
- hans_many :groups, through: :groups_users
- has_many :groups_users


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false, primary_key|
|nickname|string|null: false|

### Association
- has_many :messages
- has_many :users, through: :groups_users
- has_many :groups_users