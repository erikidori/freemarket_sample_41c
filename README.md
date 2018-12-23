## itemsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|buyer_id|integer|
|seller|references|null: false, foreign_key: true|
|status|references|null: false, foreign_key: true|
|brand_id|integer|
|category|references|null: false, foreign_key: true|

### Association
- has_many :images
- belongs_to :user
- belongs_to :brand
- belongs_to :category
- belongs_to :status



## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false|
|email|string|null: false, add_index :users, email, unique: true|
|password|string|null: false|
|mobile_number|integer|null: false, add_index :users, mobile_number, unique: true|
|payment|string|null: false|
|image|text|

### Association
- has_many :items
- has_one :sns_credential



## sns_credentialsテーブル

|Column|Type|Options|
|------|----|-------|
|uid|string|
|provider|integer|
|user_id|integer|

### Association
- belongs_to :user



## brandsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items



## categoriesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items



## statusesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items



