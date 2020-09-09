# テーブル設計

## users テーブル

| Column              | Type    | Options     |
| ------------------- | ------- | ----------- |
| nickname            | string  | null: false |
| email               | string  | null: false |
| password            | string  | null: false |
| age                 | integer | null: false |

### Association

- has_many : comics
- has_many : reviews
- has_many : buy


## comics テーブル

| Column                 | Type    | Options                         |
| ---------------------- | ------- | ------------------------------- |
| comic_name             | string  | null: false, unique: true       |
| author                 | string  | null: false                     |
| publisher              | string  | null: false                     |
| story                  | text    |                                 |
| status_id              | integer | null: false                     |
| user_id                | integer | null: false , foreign_key: true |

### Association

- belongs_to : users 
- has_many   : reviews



## reviews テーブル

| Column              | Type    | Options                         |
| ------------------- | ------- | ------------------------------- |
| rate                | float   | null: false                     |
| content             | text    |                                 |
| user_id             | integer | null: false , foreign_key: true |
| items_id            | integer | null: false , foreign_key: true |

### Association

- belongs_to : users 
- belongs_to : items
