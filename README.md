# DB設計

## users table
| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| nick_name          | string              | null: false             |
| email              | string              | null: false             |
| password           | string              | null: false             |
| last_name          | string              | null: false             |
| first_name         | string              | null: false             |
| last_name_kana     | string              | null: false             |
| first_name_kana    | string              | null: false             |
| date_of_birth      | date                | null: false             |

### Association

- has_many :items
- has_many :orders
- belongs_to :deliverys

## item table
| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| item_name          | string              | null: false             |
| item_text          | string              | null: false             |
| category           | string              | null: false             |
| usage              | string              | null: false             |
| delivery           | string              | null: false             |
| before_delivery    | string              | null: false             |
| delivery_day       | string              | null: false             |
| price              | integer             | null:false              |
| nick_name          | references          | foreign_key: true       |

### Association

- belongs_to :users
- belongs_to :orders

## orders
| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| zip                | string              | null: false             |
| after_delivery     | string              | null: false             |
| city               | string              | null: false             |
| address            | string              | null: false             |
| building           | string              |                         |
| phone_num          | string              | null: false             |
| nick_name          | references          | foreign_key: true       |

### Association

- belongs_to :users
- belongs_to :items
- has_one :deliverys

## deliverys
| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| after_delivery     | references          | foreign_key: true       |
| city               | references          | foreign_key: true       |
| address            | references          | foreign_key: true       |
| building           | references          | foreign_key: true       |
| nick_name          | references          | foreign_key: true       |


### Association

