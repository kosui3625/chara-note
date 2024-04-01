# テーブル設計

## users テーブル

| Column                         | Type    | Options     |
| ------------------------------ | ------- | ----------- |
| nickname                       | string  | null: false |
| email                          | string  | null: false, unique: true |
| encrypted_password             | string  | null: false |
| point_use_total                | integer | null: false | ## 
| point_have_total               | integer | null: false | ## 



### Association

- has_many :characters
- has_one  :story



## characters テーブル

| Column                    | Type         | Options     |
| ------------------------- | ------------ | ----------- |
| name                      | string       | null: false | ## 
| nickname                  | string       | null: false | ## 
| age                       | string       | null: false | ## 
| point_use                 | integer      | null: false | ## 
| style_id                  | integer      | null: false | ## 
| blood1_id                 | integer      | null: false | ## 
| blood2_id                 | integer      | null: false | ## 
| routes1_id                | integer      | null: false | ## 
| routes2_id                | integer      | null: false | ## 
| birth_bond                | string       | null: false | ## 
| encounter_bond            | string       | null: false | ## 
| first_ego                 | string       | null: false | ## 
| link                      | string       | null: false, foreign_key: true | ## 



### Association

- belongs_to :user
- has_many :stories

## stories テーブル

| Column                               | Type        | Options     |
| ------------------------------------ | ----------- | ----------- |
| title                                | string      | null: false |
| point_get                            | integer     | null: false |
| ho_id                                | integer     | null: false |
| ho_explain                           | integer     | null: false |
| players                              | string      | null: false |
| another_characters                   | string      | null: false |
| scenario_bond                        | string      | null: false |
| scenario_ego                         | string      | null: false |
| player_bond_1                        | string      | null: false |
| player_ego_1                         | string      | null: false |
| player_bond_2                        | string      | null: false |
| player_ego_2                         | string      | null: false |

### Association

- belongs_to :character
- has_one    :user
