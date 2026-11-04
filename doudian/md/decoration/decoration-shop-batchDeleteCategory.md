# 批量删除类目

> shop.batchDeleteCategory — 批量删除类目

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量删除类目 |
| 文档地址 | `/docs/doudian/decoration/decoration-shop-batchDeleteCategory` |
| 接口 ID | `doudian.decoration.shop.batchDeleteCategory` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/batchDeleteCategory` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6518 |
| 更新日期 | `2024-05-15` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tmp_id` | body | string | 是 | 页面id,请使用【/shop/openShopPageManagementList】接口查询页面id或访问店铺装修列表页面获取页面id。 | `735278978958386` |
| `category_id_list` | body | array | 是 | 分类id列表，如果是一级分类id会删除所有关联的二级分类。单次最多支持传100个id。 | `["735278978958382", "735278978958383"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/batchDeleteCategory?app_key=your_appkey_here&method=shop.batchDeleteCategory&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tmp_id` | string | 页面id，成功时有值。 | `7352789789583868197` |
| `category_list` | array | 一级分类列表。成功后返回页面完整分类列表。 | `` |
| `failed_category_list` | array | 失败分类列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "category_list": [
      {
        "children_category_list": [
          {
            "cid": "7352789789583868196",
            "name": "葡萄",
            "rank": "100"
          }
        ],
        "cid": "7352789789583868198",
        "name": "水果",
        "rank": "100"
      }
    ],
    "failed_category_list": [
      {
        "cid": "7352789789583868193",
        "level": "2",
        "msg": "分类不存在",
        "name": "水果"
      }
    ],
    "tmp_id": "7352789789583868197"
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
