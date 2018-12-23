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
- has_many :likes 
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
|adress|text|null:false|
|image|text|
|uid|string|
|provider|integer|


### Association
- has_many :items
- has_many :likes
- has_one :credit_card


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
|path|string|null: false|

### Association
- has_many :items



## statusesテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items



## likesテーブル

|Column|Type|Options|
|------|----|-------|
|item|references|null: false, foreign_key: true|
|user|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to : item



## credit_cardsテーブル
|Column|Type|Options|
|------|----|-------|
|name|references|null: false|
|number|references|null: false|
|expire_date|integer|null: false|
|cvv|integer|null:false|

### Association
- belongs_to :user
