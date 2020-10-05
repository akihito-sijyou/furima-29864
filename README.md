# テーブル設計

## users テーブル

| Column          | Type   | Options    |
| --------------- | ------ | ---------- |
| nickname        | string | null: false|
| first_name      | string | null: false|
| second_name     | string | null: false|
| first_furigana  | string | null: false|
| second_furigana | string | null: false|
| email           | string | null: false|
| password        | string | null: false|
| birthday        | date   | null: false|

### Association
- has_many :items
- has_many :purchase_functions

## items テーブル
| Column             | Type       | Options          |
| ------------------ | ---------- | ---------------- |
| name               | string     | null: false      |
| text               | text       | null: false      |
| category_id        | integer    | null: false      |
| price              | integer    | null: false      |
| status_id          | integer    | null: false      |
| delivery_charge_id | integer    | null: false      |
| shipping_area_id   | integer    | null: false      |
| shipping_date_id   | integer    | null: false      |
| user               | references | foreign_key: true|

### Association
- belongs_to :user
- has_one :purchase_functions

## Purchase_function　テーブル
| Column    | type       | Options          |
| --------- | ---------- | ---------------- |
| user      | references | foreign_key: true|
| item      | references | foreign_key: true|

### Association
- belongs_to :item
- belongs_to :user
- has_one :shipping_addresses

## Shipping_address テーブル
| Column            | type       | Options          |
| ----------------- | ---------- | -----------------|
| purchase_function | references | foreign_key: true|
| postal_code       | string     | null: false      |
| Prefectures_id    | integer    | null: false      |
| municipality      | string     | null: false      |
| address           | string     | null: false      |
| building_name     | string     |                  |
| phone_number      | string     | null: false      |

### Association
- belongs_to　：purchase_function