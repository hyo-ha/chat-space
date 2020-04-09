
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many:groups,through:group_users
- has_many:messages
- has_many:group_users

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|user|references|null:false,foreign_key|
|group|references|null:false,foreign_key|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|

### Association
- has_many: users, through: group_users
- has_many: group_users
- has_many:messages
