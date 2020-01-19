## README
## messageテーブル
|Column|Type|Options|
|------|----|-------|
|content|text||
|image|string||
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|index: true|
|email|string|null: false, unique: true|
### Association
- has_many :groups_users
- has_many :groups, through: groups_users
- has_many :messages
## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|unique: true|
### Association
- has_many :groups_users
- has_many :users, through: groups_users
- has_many :messages
## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

## 