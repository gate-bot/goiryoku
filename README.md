## users テーブル

| Column             | Type       | Options                   |
| -----------------  | ---------- | ------------------------- |
| name               | string     | null: false               |
| email              | string     | null: false, unique: true |
| encrypted_password | string     | null: false               |
| profile            | text       | null: false               |


### Association

- has_many :words
- has_many :books
- has_many :videos
- has_many :others 
- has_many :comments

## words テーブル

| Column           | Type       | Options           |
| ---------------- | ---------- | ----------------- |
| word             | string     | null: false       |


### Association

- belongs_to :user
- has_one :comments


## comments テーブル

| Column           | Type       | Options           |
| ---------------- | ---------- | ----------------- |
| comment          | text       | null: false       |


### Association

- belongs_to :user
- belongs_to :word


## books テーブル

| Column        | Type       | Options           |
| ------------- | ---------- | ----------------- |
| book_name     | string     | null: false       |
| writer        | string     |                   |
| book_url      | string     |                   |


### Association

- belongs_to :user


## videos テーブル

| Column        | Type       | Options           |
| ------------- | ---------- | ----------------- |
| video_name    | string     | null: false       |
| video_url     | text       | null: false       |


### Association

- belongs_to :user



## others テーブル

| Column        | Type       | Options           |
| ------------- | ---------- | ----------------- |
| other_name    | string     | null: false       |


### Association

- belongs_to :user