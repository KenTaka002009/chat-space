# messagestable
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

# users table
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false, index: true|


## Association
- has_many:groups, through: :members
- has_many:messages
- has_many:members

# groupstable
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

## Association
- has_many:users, through: :members
- has_many:messages
- has_many:members

# memberstable
|Column|Type|Options|
|------|----|-------|
|group|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user