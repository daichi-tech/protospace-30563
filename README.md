# テーブル設計

## usersテーブル

| Column     | Type   | Options     |
| --------   | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has many :prototypes
- has many :comments

## prototypesテーブル

| Column     | Type                | Options     |
| --------   | ------              | ----------- |
| title      | string              | null: false |
| catch_copy | text                | null: false |
| concept    | text                | null: false |
| image      | ActiveStorageで実装  |             |
| user       | references          |             |

### Association

- belongs to :user
- has many   :comment

## commentsテーブル

| Column    | Type       | Options     |
| --------  | ------     | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### Association

- belongs to :user
- belongs to :prototype