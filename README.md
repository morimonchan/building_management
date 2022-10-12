# README

#users テーブル

| Column             | Type   | Options                |
| ------------------ | ------ | -----------            |
| name               | string | null: false            |
| employee_number    | integer| null: false            |
| encrypted_password | string | null: false default: ""|

- has_many :comments
- has_many :buildings


#buildingsテーブル
| Column         | Type      | Options                |
| -------------- | ------    | -----------            |
| building_name  | string    | null: false            |
| place_id       | integer   | null: false            |
| address        | string    | null: false            |
| building_detail| text      | null: false            |
| user           | references| null: false foreign_key: true           |

- belongs_to :user
- has_many :comments 
- has_one    :vacancy
- has_one    :parking

#comments テーブル
| Column    | Type       | Options     |
| ----------| -------    | ----------- |
| user      | references | null: false  foreign_key: true           |
| building  | references | null: false  foreign_key: true           |
| content   | text       | null: false |

- belongs_to :user
- belongs_to :building



#parkings テーブル
| Column           | Type       | Options        |
| ---------------- | -------    | -----------    |
| parking_number   | integer    | null: false    |
| price            | integer    | null: false    |
| parking_detail   | text       | null: false    |
| building         | references | null: false  foreign_key: true           |

- belongs_to :building



#vacancies テーブル
| Column             | Type      | Options         |
| ------------------ | -------   | -----------     |
| room_number        | integer   | null: false     |
| deadline           | date      | null: false     |
| floor_plan         | string    |  null: false    |
| deposit            | integer   | null: false     |
| rent               | integer   | null:false      |
| service_fee        | integer   | null: false     |
| membership_fee     | integer   | null: false     |
| building           | references| null: false   foreign_key: true    |

- belongs_to :building


