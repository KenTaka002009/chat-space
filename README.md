# messagestable
|Column||Type||Option|
|-------------------|
|body||text|
|image||string|
|group||references|null: false, foreign_key: true|
|user||references|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

# users table
|Column||Type||Option|
|-------------------|
|nickname||string||null: false, index: true|


## Association
- has_many:groups, through: :members
- has_many:messages
- has_many:members

# grouptable
|Column||Type||Option|
|-------------------|
|name||string||null: false|

## Association
- has_many:users, through: :members
- has_many:messages
- has_many:members

# memberstable
|Column||Type||Option|
|-------------------|
|group||references||null: false, foreign_key: true|
|user||references||null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user