# テーブル設計

## users テーブル

| Column   | Type   | Options    |
| -------- | ------ | ---------- |
| name     | string | null: false|
| email    | string | null: false|
| password | string | null: false|
| birthday | date   | null: false|

### Association
- has_many :items

## items テーブル
| Column          | Type       | Options    |
| --------------- | ---------- | ---------- |
| item_name       | string     | null: false|
| item_text       | text       | null: false|
| category        | string     | null: false|
| price           | integer    | null: false|
| image           | string     | null: false|
| status          | string     | null: false|
| delivery_charge | string     | null: false|
| shipping_area   | integer    | null: false|
| shipping_date   | date       | null: false|
| users_id        | references | null: false|

### Association
- belongs_to :user

## Purchase function　テーブル
| Column    | type       | Options    |
| --------- | ---------- | ---------- |
| users_id  | references | null: false|
| items_id  | references | null: false|

### Association
- has_one :shipping address

## Shipping address テーブル
| Column    | type       | Options    |
| --------- | ---------- | ---------- |
| users_id  | references | null: false|

### Association
- belongs_to　：purchase function