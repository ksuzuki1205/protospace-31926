# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------  | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many :comments
- has_many :prototypes


## comments テーブル

| Column    | Type         | Options     |
| --------- | ------------ | ----------- |
| text      | text         | null: false |
| user      | references   | null: false |
| prototype | references   | null: false |


### Association
- belongs_to :user
- belongs_to :prototype



## prototypes テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | references | null: false                    |
| image      |            |                                | ActiveStrageで実装
| user       | references |                                |


### Association

- belongs_to :user
- has_many :comments
