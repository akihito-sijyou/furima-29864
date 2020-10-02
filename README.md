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
- has_one :purchase_function

## items テーブル
| Column          | Type       | Options          |
| --------------- | ---------- | ---------------- |
| name            | string     | null: false      |
| text            | text       | null: false      |
| category_id     | integer    | null: false      |
| price           | integer    | null: false      |
| image           | string     | null: false      |
| status          | integer    | null: false      |
| delivery_charge | integer    | null: false      |
| shipping_area   | integer    | null: false      |
| shipping_date   | integer    | null: false      |
| user            | references | foreign_key: true|

### Association
- belongs_to :user
- has_one :purchase_function

## Purchase_function　テーブル
| Column    | type       | Options          |
| --------- | ---------- | ---------------- |
| user      | references | foreign_key: true|
| item      | references | foreign_key: true|

### Association
- belongs_to :items
- belongs_to :user
- has_one :shipping address

## Shipping_address テーブル
| Column          | type       | Options          |
| --------------- | ---------- | -----------------|
| user            | references | foreign_key: true|
| postal_code     | string     | null: false      |
| Prefectures_id  | integer    | null: false      |
| municipality    | string     | null: false      |
| address         | string     | null: false      |
| building_name   | string     | null: false      |
| phone_number    | string     | null: false      |

### Association
- belongs_to　：purchase function