# anyone
 
## users テーブル

| column   	| type   	| options    	|
|----------	|--------	|------------	|
| email    	| string 	| null:false 	|
| password 	| string 	| null:false 	|

### Association
  
-has_many:tickets
-has_many:orders

## tickets テーブル

| column 	| type    	| options    	|
|--------	|---------	|------------	|
| join   	| integer 	| null:false 	|

### Association
  
-belongs_to:user
-has_one:order

## orders テーブル

| column    | type      | options                         |
|---------- |---------  |-------------------------------  |
| user_id   | integer   | null:false, foreign_key: true   |
| ticket_id | integer   | null:false, foreign_key: true   |

### Association

-belongs_to:user
-belongs_to:ticket dependent: :destroy