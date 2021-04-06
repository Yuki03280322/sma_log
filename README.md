# Table design

## users table

| Column             | Type       | Options        |
| ------------------ | ---------- | ---------------|
| id                 | bigint     | auto_increment |
| email              | varchar    | null: false    |
| password           | varchar    | null: false    |
| name               | varchar    | null: false    |

### Association
- has_many :friends
- has_many :battles

## friends table

| Column             | Type       | Options        |
| ------------------ | ---------- | ---------------|
| id                 | bigint     | auto_increment |
| name               | varchar    | null: false    |

### Association
- belongs_to :user
- has_many :battles

## battles table

| Column             | Type       | Options        |
| ------------------ | ---------- | ---------------|
| id                 | bigint     | auto_increment |
| format             | varchar    | null: false    |
| rule               | varchar    | null: false    |
| result             | varchar    | null: false    |
| opponent_chara_id  | unbigint   | null: false    |
| my_chara_id        | unbigint   | null: false    |
| user_id            | unbigint   | null: false    |
| friend_id          | unbigint   |                |
| created_at         | timestamp  | null: false    |

### Association
- belongs_to :user
- belongs_to :friend
- belongs_to :my_chara
- belongs_to :opponent_cahra

## my_charas table

| Column             | Type       | Options        |
| ------------------ | ---------- | ---------------|
| id                 | bigint     |                |
| chara              | varchar    | null: false    |
| url                | varchar    | null: false    |

### Association
- has_many :battles

## opponent_charas table

| Column             | Type       | Options        |
| ------------------ | ---------- | ---------------|
| id                 | bigint     |                |
| chara              | varchar    | null: false    |
| url                | varchar    | null: false    |

### Association
- has_many :battles