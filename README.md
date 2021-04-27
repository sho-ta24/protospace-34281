# テーブル設計

## users テーブル

| Column     | Type   | Options  |
| ---------- | ------ | -------- |
| email      | string | not null |
| password   | string | not null |
| name       | string | not null |
| profile    | text   | not null |
| occupation | text   | not null |
| position | text   | not null |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type          | Options  |
| ---------- | ------------- | -------- |
| title      | string        | not null |
| catch_copy | text          | not null |
| concept    | text          | not null |
| image      | ActiveStorage |          |
| user       | references    |          |

### Association

- belongs_to :user
- has_many :comments

##　comments テーブル

| Column     | Type          | Options  |
| ---------- | ------------- | -------- |
| text       | string        | not null |
| user       | references    |          |
| prototype  | references    |          |

### Association

- belongs_to :user
- belongs_to :prototypes
