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
| name                      | string       | null: false |
| nickname                  | string       | null: false |
| age                       | string       | null: false |
| setting                   | text         | null: false |
| point_use                 | integer      | null: false |
| style_id                  | integer      | null: false |
| blood1_id                 | integer      | null: false |
| blood2_id                 | integer      | null: false |
| routes1_id                | integer      | null: false |
| routes2_id                | integer      | null: false |
| birth_bond                | string       | null: false |
| encounter_bond            | string       | null: false |
| first_ego                 | string       | null: false |
| link                      | string       | foreign_key: true |



### Association

- belongs_to :user
- has_many :stories

## stories テーブル

| Column                               | Type        | Options           |
| ------------------------------------ | ----------- | ----------------- |
| title                                | string      | null: false       |
| point_get                            | string      | foreign_key: true |
| point_consume                        | string      | foreign_key: true |
| ho_id                                | integer     | foreign_key: true |
| ho_explain                           | integer     | null: false       |
| birth_ego                            | string      | foreign_key: true |
| encounter_ego                        | string      | foreign_key: true |
| scenario_bond                        | string      | null: false       |
| scenario_ego                         | string      | foreign_key: true |
| player_bond_1                        | string      | foreign_key: true |
| player_ego_1                         | string      | foreign_key: true |
| player_bond_2                        | string      | foreign_key: true |
| player_ego_2                         | string      | foreign_key: true |
| another_player_1                     | string      | foreign_key: true |
| another_character_1                  | string      | foreign_key: true |
| another_player_2                     | string      | foreign_key: true |
| another_character_2                  | string      | foreign_key: true |
| another_player_3                     | string      | foreign_key: true |
| another_character_3                  | string      | foreign_key: true |
| another_player_4                     | string      | foreign_key: true |
| another_character_4                  | string      | foreign_key: true |
| another_player_5                     | string      | foreign_key: true |
| another_character_5                  | string      | foreign_key: true |
| what_new                             | text        | foreign_key: true |
| other                                | text        | foreign_key: true |

### Association

- belongs_to :character
- has_one    :user
