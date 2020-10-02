# テーブル設計

## users テーブル

| Column          | Type   | Options    |
| --------------- | ------ | ---------- |
| nickname        | string | null: false|
| first name      | string | null: false|
| second name     | string | null: false|
| first furigana  | string | null: false|
| second furigana | string | null: false|
| email           | string | null: false|
| password        | string | null: false|
| birthday        | date   | null: false|

### Association
- has_many :items

## items テーブル
| Column          | Type       | Options    |
| --------------- | ---------- | ---------- |
| name      　　　 | string     | null: false|
| text   　　　    | text       | null: false|
| category        | string     | null: false|
| price           | integer    | null: false|
| image           | string     | null: false|
| status          | integer    | null: false|
| delivery_charge | integer    | null: false|
| shipping_area   | integer    | null: false|
| shipping_date   | integer    | null: false|
| users           | references | null: false|

### Association
- belongs_to :user

## Purchase function　テーブル
| Column    | type       | Options          |
| --------- | ---------- | ---------------- |
| users     | references | foreign_key: true|
| items     | references | foreign_key: true|

### Association
- has_one :shipping address

## Shipping address テーブル
| Column        | type       | Options          |
| --------------| ---------- | -----------------|
| users         | references | foreign_key: true|
| postal code   | integer    | null: false      |
| Prefectures   | string     | null: false      |
| municipality  | string     | null: false      |
| address       | string     | null: false      |
| building name | string     | null: false      |
| phone number  | integer    | null: false      |

### Association
- belongs_to　：purchase function