# product.commentCounter

> 获取商品维度或者店铺维度的评价计数信息、或者是印象词信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.permission.product.commentCounter` |
| 中文名 | 获取商品维度或者店铺维度的评价计数信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/commentCounter` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/7909 |
| 更新日期 | `2025-12-02` |

## 接口说明

- 文档书: 二方开放权限组（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `basic_info` | body | object | 否 | 请求的基本信息 | `` |
| `  └ shop_ids` | body | array | 否 | 店铺id列表 | `1` |
| `  └ user_ids` | body | array | 否 | 用户id列表 | `1` |
| `  └ offset` | body | mixed | 否 | offset | `1` |
| `  └ app_id` | body | mixed | 否 | appid | `1` |
| `  └ device_id` | body | mixed | 否 | 设备id | `1` |
| `  └ order_ids` | body | array | 否 | 订单id列表 | `1` |
| `  └ count` | body | mixed | 否 | count | `1` |
| `  └ sort` | body | mixed | 否 | 排序方式 | `1` |
| `  └ product_ids` | body | array | 否 | 商品id列表 | `1` |
| `  └ kol_ids` | body | array | 否 | 达人id列表 | `1` |
| `  └ user_id` | body | mixed | 否 | 当前请求人的user_id | `1` |
| `  └ from_kol_id` | body | mixed | 否 | 算法用 | `1` |
| `counter_opt` | body | object | 否 | 【计数选项】 | `` |
| `  └ photos` | body | boolean | 否 | 获取有图数 | `1` |
| `  └ mid` | body | boolean | 否 | 获取中评数 | `1` |
| `  └ video` | body | boolean | 否 | 获取有视频数 | `1` |
| `  └ good` | body | boolean | 否 | 获取好评数 | `1` |
| `  └ rule_string` | body | string | 否 | 对于复杂的查询条件，可以直接传入约定的【规则字符串】，评价服务根据【规则字符串】查询对应的标签组名 | `1` |
| `  └ need_has_word_count` | body | boolean | 否 | 需要有字评价数 | `1` |
| `  └ has_meaning` | body | boolean | 否 | 需要获取有意义的计数 | `1` |
| `  └ need_detailed_count` | body | boolean | 否 | 需要获取详实评价数 | `1` |
| `  └ photo_video` | body | boolean | 否 | 获取有图/视频的数量 | `1` |
| `  └ total` | body | boolean | 否 | 获取评价总数 | `1` |
| `  └ sku` | body | array | 否 | 只获取sku下的计数 | `1` |
| `  └ bad` | body | boolean | 否 | 获取差评数 | `1` |
| `  └ virtual_main` | body | boolean | 否 | 虚拟主评/逾期追评数量 | `1` |
| `  └ has_meaningless` | body | boolean | 否 | 需要获取无意义的计数 | `1` |
| `  └ selection` | body | boolean | 否 | 获取买家秀数量 | `1` |
| `  └ append` | body | boolean | 否 | 获取有追评的数量 | `1` |
| `biz_scene` | body | string | 否 | 业务场景 | `1` |
| `impression_opt` | body | object | 否 | 【印象词选项】 | `` |
| `  └ need_refine_sort` | body | boolean | 否 | 是否需要算法精排序（默认排序是按照印象词数量从大到小排序） | `1` |
| `  └ exclude_product_id` | body | mixed | 否 | 获取店铺印象词时，需要排除的商品id（店铺维度生效） | `1` |
| `  └ sku` | body | array | 否 | 获取sku下的印象词 | `1` |
| `  └ count_limit` | body | mixed | 否 | 需要的印象词个数，0表示不限制个数 | `1` |
| `  └ only_positive` | body | boolean | 否 | 只要正向印象词 | `1` |
| `  └ show_common_first` | body | boolean | 否 | 是否优先展示通用印象词（店铺维度生效） | `1` |
| `  └ impression_version` | body | mixed | 否 | 印象词版本号，默认是v1 | `1` |
| `  └ only_negative` | body | boolean | 否 | 只要负向印象词 | `1` |
| `  └ stat_id` | body | mixed | 否 | 评价一级tab，1-8 对应 全部/有图/好评/中评/追评/差评/最新/中差评 | `1` |
| `extra` | body | string | 否 | 额外的入参 | `1` |
| `req_ctx` | body | object | 否 | 1 | `` |
| `  └ host_app_version` | body | string | 否 | 宿主（源）版本号 | `1` |
| `  └ iid` | body | string | 否 | 11 | `1` |
| `  └ os_name` | body | string | 否 | 1 | `1` |
| `  └ app_version` | body | string | 否 | 1 | `1` |
| `  └ version_name` | body | string | 否 | 1 | `1` |
| `  └ device_platform` | body | string | 否 | 1 | `1` |
| `  └ ab_context` | body | string | 否 | 1 | `1` |
| `  └ user_id` | body | mixed | 否 | 1 | `1` |
| `  └ ab_param` | body | string | 否 | AB参数 | `1` |
| `  └ device_id` | body | mixed | 否 | 1 | `1` |
| `  └ entrance` | body | string | 否 | 请求入口，list:列表页，detail:商详页，shoplist:店铺列表 | `1` |
| `  └ priority_region` | body | string | 否 | 1 | `1` |
| `  └ channel` | body | string | 否 | 1 | `1` |
| `  └ user_type` | body | mixed | 否 | 1 | `1` |
| `  └ biz` | body | string | 否 | 1 | `1` |
| `  └ user_agent` | body | string | 否 | 1 | `1` |
| `  └ version_code` | body | string | 否 | 1 | `1` |
| `  └ host_app_id` | body | mixed | 否 | 宿主（源）appid | `1` |
| `  └ device_type` | body | string | 否 | 1 | `1` |
| `  └ saas_app_id` | body | mixed | 否 | saas端appid，不传表示不是saas场景，传7386表示当前为saas场景，传入的情况下app_id作为映射id，host_app_id作为原appid | `1` |
| `  └ app_id` | body | mixed | 否 | 1 | `1` |
| `  └ x_forwarded_for` | body | string | 否 | 1 | `1` |
| `  └ access_type` | body | string | 否 | 1 | `1` |
| `  └ x_real_ip` | body | string | 否 | 1 | `1` |
| `  └ update_version_code` | body | mixed | 否 | 1 | `1` |
| `  └ os_version` | body | string | 否 | 1 | `1` |
| `  └ app_name_` | body | string | 否 | 1 | `1` |
| `dimension` | body | mixed | 否 | 需要获取的评价计数/印象词的维度 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/commentCounter?app_key=your_appkey_here&method=product.commentCounter&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `impression_tags` | string | 印象词 | `1` |
| `agg_map` | string | 基础计数数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "agg_map": {},
    "impression_tags": {}
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
