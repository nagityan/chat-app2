# README


## usersテーブル
|  Column  |  type  |  Options|
| ---- | ---- | ---- |
|  name  |  string  | null: false|
|  email  |  string  | null: false|
|  password  |  string  | null: false|

### Association
- has_many :room-user
- has_many :rooms trough room-users
- has_many :messages


## room-userテーブル
|  Column  |  type  |  Options|
| ---- | ---- | ---- |
|  room-id  |  reference  | null: false, foreign_key: true|
|  user-id  |  reference  | null: false, foreign_key: true|


### Association
- belongs_to :user
- belongs_to :room


## roomテーブル
|  Column  |  type  |  Options|
| ---- | ---- | ---- |
|  name  |  string  | null: false|

### Association
- has_many :room-user
- has_many :users trough room-users
- has_many :messages

## messagesテーブル
|  Column  |  type  |  Options|
| ---- | ---- | ---- |
|  content  |  string  | null: false|
|  room-id  |  reference  | null: false, foreign_key: true|
|  user-id  |  reference  | null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :room


