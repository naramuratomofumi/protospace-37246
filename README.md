# README

## users テーブル

| column             | type   | options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association
- has_many :prototypes
- has_many :comments

## comments テーブル

| column    | type       | options                        |
| --------- | ---------- | ------------------------------ |
| content   | text       | null: false                    |
| prototype | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

### Association
- belongs_to :user
- belongs_to :prototype


## prototypes テーブル

| column     | type       | options                        |
| ---------- | ---------- | ------------------------------ |
| title      | text       | null: false                    |
| catch_copy | references | null: false                    |
| concept    | references | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association
- has_many :comments
- belongs_to :user

