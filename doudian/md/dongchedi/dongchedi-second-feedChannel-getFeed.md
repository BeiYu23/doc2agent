# second.feedChannel.getFeed

> 【二方接口】Feed2.0接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.feedChannel.getFeed` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/feedChannel/getFeed` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6881 |
| 更新日期 | `2024-09-14` |

## 接口说明

- 文档书: 懂车帝业务（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `config_params` | body | string | 否 | config_params | `config_params` |
| `biz_identity` | body | object | 否 | biz_identity | `` |
| `  └ biz_code` | body | string | 否 | biz_code | `biz_code` |
| `  └ scene_code` | body | string | 否 | scene_code | `scene_code` |
| `base_params` | body | object | 否 | base_params | `` |
| `  └ user_params` | body | object | 否 | user_params | `` |
| `    └ is_auth` | body | mixed | 否 | is_auth | `11` |
| `    └ register_time` | body | mixed | 否 | register_time | `1788877677` |
| `    └ is_login` | body | boolean | 否 | is_login | `false` |
| `    └ user_id` | body | mixed | 否 | user_id | `xxxxxxxxxx` |
| `    └ user_type` | body | mixed | 否 | user_type | `1` |
| `  └ device_params` | body | object | 否 | device_params | `` |
| `    └ device_score` | body | string | 否 | device_score | `device_score1` |
| `    └ language` | body | string | 否 | language | `language` |
| `    └ user_agent` | body | string | 否 | user_agent | `user_agent` |
| `    └ forwarded` | body | string | 否 | forwarde | `forwarded` |
| `    └ device_type` | body | string | 否 | device_type | `device_type` |
| `    └ device_brand` | body | string | 否 | device_brand | `device_brand` |
| `    └ os_version` | body | string | 否 | os_version | `os_version` |
| `    └ access_type` | body | string | 否 | access_type | `access_type` |
| `    └ resolution` | body | string | 否 | resolution | `resolution` |
| `    └ client_ip` | body | string | 否 | client_ip | `client_ip` |
| `    └ device_id` | body | mixed | 否 | device_id | `device_id` |
| `    └ device_platform` | body | string | 否 | device_platform | `device_platform` |
| `    └ ac` | body | mixed | 否 | ac | `ac` |
| `  └ install_params` | body | object | 否 | install_params | `` |
| `    └ app_engine` | body | string | 否 | app_engine | `app_engine` |
| `    └ app_name_` | body | string | 否 | app_name_ | `app_name_` |
| `    └ update_version_code` | body | mixed | 否 | update_version_code | `update_version_code` |
| `    └ version_name` | body | string | 否 | version_name | `version_name` |
| `    └ app_id` | body | mixed | 否 | app_id | `app_id` |
| `    └ first_install_time` | body | mixed | 否 | first_install_time | `first_install_time` |
| `    └ install_id` | body | string | 否 | install_id | `install_id` |
| `    └ install_time` | body | mixed | 否 | install_time | `install_time` |
| `    └ install_channel` | body | string | 否 | install_channel | `install_channel` |
| `    └ client_version` | body | mixed | 否 | client_version | `client_version` |
| `  └ location_params` | body | object | 否 | location_params | `` |
| `    └ longitude_value` | body | string | 否 | longitude_value | `longitude_value` |
| `    └ country` | body | string | 否 | country | `country` |
| `    └ region_id` | body | mixed | 否 | region_id | `region_id` |
| `    └ city_id` | body | mixed | 否 | city_id | `city_id` |
| `    └ city_code` | body | string | 否 | city_code | `city_code` |
| `    └ ec_address_data` | body | string | 否 | ec_address_data | `ec_address_data` |
| `    └ city` | body | string | 否 | city | `city` |
| `    └ latitude_value` | body | string | 否 | latitude_value | `latitude_value` |
| `    └ region` | body | string | 否 | region | `region` |
| `    └ country_id` | body | mixed | 否 | country_id | `country_id` |
| `    └ region_code` | body | string | 否 | region_code | `region_code` |
| `    └ country_code` | body | string | 否 | country_code | `country_code` |
| `  └ mall_ab_result` | body | object | 否 | mall_ab_result | `` |
| `    └ ab_string` | body | string | 否 | ab_string | `ab_string` |
| `    └ ab_err_string` | body | string | 否 | ab_err_string | `ab_err_string` |
| `    └ ab_result_map` | body | string | 否 | ab_result_map | `ab_result_map` |
| `  └ customed_base_params` | body | string | 否 | customed_base_params | `customed_base_params` |
| `page_params` | body | object | 否 | page_params | `` |
| `  └ refresh_type` | body | mixed | 否 | refresh_type | `refresh_type` |
| `  └ page_name` | body | string | 否 | page_name | `page_name` |
| `  └ enter_from` | body | string | 否 | enter_from | `enter_from` |
| `  └ tab_id` | body | mixed | 否 | tab_id | `tab_id` |
| `  └ real_count` | body | mixed | 否 | 精排数量，仅用于推荐侧合理分配精排资源 | `1` |
| `  └ count` | body | mixed | 否 | count | `1` |
| `  └ post_back` | body | string | 否 | 首次进入和下拉刷新传空 | `xxx` |
| `recall_params` | body | object | 否 | recall_params | `` |
| `  └ recommend_params` | body | object | 否 | recommend_params | `` |
| `    └ disable_personal_recommend` | body | boolean | 否 | disable_personal_recommend | `false` |
| `    └ recommend_filter` | body | object | 否 | recommend_filter | `` |
| `      └ related_gid` | body | mixed | 否 | related_gid | `1` |
| `    └ recommend_customed` | body | string | 否 | recommend_customed | `xxxx` |
| `  └ unlike_params` | body | object | 否 | unlike_params | `` |
| `    └ unlike_datas` | body | array | 否 | unlike_datas | `xxxx` |
| `  └ last_action_params` | body | object | 否 | last_action_params | `` |
| `    └ last_action_datas` | body | array | 否 | last_action_datas | `last_action_datas` |
| `  └ tabs_params` | body | object | 否 | tabs_params | `` |
| `    └ with_tabs` | body | boolean | 否 | with_tabs | `with_tabs` |
| `impression_params` | body | object | 否 | impression_params | `` |
| `  └ impression_datas` | body | array | 否 | impression_datas | `xxxx` |
| `  └ impression_start_time` | body | mixed | 否 | impression_start_time | `188777777` |
| `force_insert_params` | body | object | 否 | force_insert_params | `` |
| `  └ force_insert_items` | body | array | 否 | force_insert_items | `` |
| `    └ force_insert_type` | body | mixed | 否 | force_insert_type | `1` |
| `    └ force_insert_position` | body | mixed | 否 | force_insert_position | `1` |
| `    └ force_insert_feed_type` | body | mixed | 否 | force_insert_feed_type | `1` |
| `    └ force_insert_feed_id` | body | string | 否 | force_insert_feed_id | `xxxx` |
| `    └ force_insert_customed` | body | string | 否 | force_insert_customed | `xxxx` |
| `  └ disable_intervene` | body | boolean | 否 | disable_intervene | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/feedChannel/getFeed?app_key=your_appkey_here&method=second.feedChannel.getFeed&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `feed` | array | pack_data_v1 | `` |
| `page` | object | page | `` |
| `filtered_feed` | array | filtered_feed | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "feed": [
      {
        "id": "1",
        "pack_data_v1": {
          "product": {
            "cover": {
              "height": "100",
              "uri": "xxxx",
              "url_list": "xxxx",
              "width": "100"
            },
            "id": "xxxxx",
            "price": {
              "market_price": "1",
              "max_price": "1",
              "min_price": "1",
              "original_price": "2",
              "show_price": "1",
              "show_price_type": "xxx",
              "show_sku_id": "xxx",
              "type": "1",
              "type_text": "type_text"
            },
            "title": "xxxxx"
          }
        },
        "source": "1",
        "type": "1"
      }
    ],
    "filtered_feed": [
      {
        "id": "id",
        "pack_data_v1": {
          "product": {
            "cover": {
              "height": "height",
              "uri": "uri",
              "url_list": "url_list",
              "width": "width"
            },
            "id": "id",
            "price": {
              "market_price": "market_price",
              "max_price": "max_price",
              "min_price": "min_price",
              "original_price": "1",
              "show_price": "1",
              "show_price_type": "xxxx",
              "show_sku_id": "xxxx",
              "type": "type",
              "type_text": "type_text"
            },
            "title": "title"
          }
        },
        "source": "source",
        "type": "type"
      }
    ],
    "page": {
      "more": "true",
      "post_back": "post_back"
    }
  },
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
