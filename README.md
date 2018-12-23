## itemsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|price|integer|null: false|
|buyer_id|integer|
|seller|references|null: false, foreign_key: true|
|status|string|null: false|
|brand_id|integer|
|category|references|null: false, foreign_key: true|

### Association
- has_many :images
- has_many :likes 
- has_many :comments
- belongs_to :user
- belongs_to :brand
- belongs_to :category
- belongs_to :status



## usersテーブル

|Column|Type|Options|
|------|----|-------|
|last_name|varchar|null: false|
|first_name|varchar|null: false|
|last_name_kana|varchar|null: false|
|first_name_kana|varchar|null: false|
|nickname|varchar|null: false|
|email|varchar|null: false, add_index :users, email, unique: true|
|password|varchar|null: false|
|phone_number|varchar|null: false, add_index :users, mobile_number, unique: true|
|payment|string|null: false|
|postcode|varchar|null:false|
|prefecture|varchar|null:false|
|city|varchar|null:false|
|block|varchar|null:false|
|building|varchar|
|birthday|date|null:false|
|avatar_image|text|
|uid|varchar|
|provider|varchar|


### Association
- has_many :items
- has_many :likes
- has_many :comments
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
|name|string|null: false|
|number|integer|null: false|
|expire_date|integer|null: false|
|cvv|integer|null:false|

### Association
- belongs_to :user



## commnetsテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|user|references|null: false, foreign_key: true|
|item|references|null: false, foreign_key: true|


### Association
- belongs_to :user
- belongs_to :item
