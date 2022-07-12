
# テーブル設計

## users テーブル

| Column             | Type   | Options                 | 
| ------------------ | ------ | ----------------------- | 
| email              | string | null: false,default: "" |
| encrypted_password | string | null: false             |
| name               | string | null: false             |
| profile            | text   | null: false             |
| occupation         | text   | null: false             |
| position           | text   | null: false             |

### Association

- has_many :comments
- has_many :prototypes


##  commentsテーブル

| Column    | Type      | Options                        |
| --------- | --------- | ------------------------------ |
| content   | text      | null: false                    |
| prototype | reference | null: false, foreign_key: true |
| user      | reference | null: false, foreign_key: true |

### Association
- belongs_to :prototypes
- belongs_to :user

## prototypes テーブル

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| title           | string     | null: false                    |
| catch_copy      | text       | null: false                    |
| concept         | text       | null: false                    |
| user            | references | null: false, foreign_key: true |

### Association
- has_many :comments
- belongs_to :users


