# DB設計

## users table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nick_name          | string              | null: false             |
| email              | string              | null: false             |
| encrypted_password | string              | null: false             |
| last_name          | string              | null: false             |
| first_name         | string              | null: false             |
| last_name_reading  | string              | null: false             |
| first_name_reading | string              | null: false             |
| date_of_birth      | date                | null: false             |

### Association

- has_many :items
- has_many :buys

## item table

| Column               | Type                | Options                 |
|----------------------|---------------------|-------------------------|
| name                 | string              | null: false             |
| text                 | text                | null: false             |
| category_id          | integer             | null: false             |
| usage_id             | integer             | null: false             |
| delivery_fee_id      | integer             | null: false             |
| prefecture_id        | integer             | null: false             |
| delivery_day_id      | integer             | null: false             |
| price                | integer             | null:false              |
| user                 | references          | foreign_key: true       |

### Association

- belongs_to :user
- has_one :buy

## buys table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| user               | references          | foreign_key: true       |
| item               | references          | foreign_key: true       |

### Association

- belongs_to :user
- belongs_to :item
- has_one :delivery

## deliverys table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| postal_code        | string              | null: false             |
| prefecture_id      | integer             | null: false             |
| city               | string              | null: false             |
| house_number       | string              | null: false             |
| building_name      | string              |                         |
| phone_num          | string              | null: false             |
| buy                | references          | foreign_key :true       |



### Association

- belongs_to :buy