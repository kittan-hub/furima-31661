# DB設計

## users table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nick_name          | string              | null: false             |
| email              | string              | null: false             |
| encryped_password  | string              | null: false             |
| last_name          | string              | null: false             |
| first_name         | string              | null: false             |
| last_name_reading  | string              | null: false             |
| first_name_reading | string              | null: false             |
| date_of_birth      | date                | null: false             |

### Association

- has_many :items
- has_many :orders

## item table

| Column               | Type                | Options                 |
|----------------------|---------------------|-------------------------|
| name                 | string              | null: false             |
| text                 | string              | null: false             |
| category_id          | integer             | null: false             |
| usage_id             | integer             | null: false             |
| delivery_fee_id      | integer             | null: false             |
| before_prefecture_id | integer             | null: false             |
| delivery_day_id      | integer             | null: false             |
| price                | integer             | null:false              |

### Association

- belongs_to :user
- has_one :order

## orders table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nick_name_id       | references          | foreign_key: true       |
| nick_name_id       | references          | foreign_key: true       |

### Association

- belongs_to :user
- belongs_to :item
- has_one :delivery

## deliverys table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| postal_code        | string              | null: false             |
| after_delivery     | string              | null: false             |
| city               | string              | null: false             |
| house_number       | string              | null: false             |
| building_name      | string              |                         |
| phone_num          | string              | null: false             |



### Association

- belongs_to :order