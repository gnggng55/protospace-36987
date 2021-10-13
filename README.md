# README

## users テーブル

| Column             | Type   | Opinions    |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| name               | string | null: false |
| prifile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |
 
### Association

- has_many :protos
- has_many :comments


## proto テーブル

| Column     | Type          | Options                        |
| ---------- | ------------- | ------------------------------ |
| title      | string        | null: false, foreign_key :true |
| catch_copy | text          | null: false, foreign_key :true |
| concept    | text          | null: false, foreign_key :true |
| image      | ActiveStorage | null: false, foreign_key :true |

### Association

- belongs_to : user
- has_many :comments


## comments テーブル

| Column      | Type      | Options                        |
| ----------- | --------- | ------------------------------ |
| user_id     | reference | null; false, foreign_key: true |
| proto_id    | reference | null: false, foreign_key: true | 
| content     | text      | null; false                    |

### Association

- belongs_to :user
- belongs_to :proto