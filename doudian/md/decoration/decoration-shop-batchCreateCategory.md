# shop.batchCreateCategory

> 批量创建类目接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.batchCreateCategory` |
| 中文名 | 批量创建类目 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/batchCreateCategory` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6439 |
| 更新日期 | `2024-04-18` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tmp_id` | body | string | 是 | 页面id,请使用【/shop/openShopPageManagementList】接口查询页面id或访问店铺装修列表页面获取页面id。 | `735278978958386` |
| `category_info_list` | body | array | 是 | 一级页面分类列表，最大支持一次传入一级+二级类目总数500个。 | `` |
| `  └ children_category_list` | body | array | 否 | 二级页面分类列表 | `` |
| `    └ rank` | body | mixed | 否 | 页面类目排序字段，在同级别优先级权重，越大则越靠前，可选范围[100000]，相同排序数字，创建时间最新的靠前排列。0排序在最后面，以此类推。 | `100` |
| `    └ name` | body | string | 是 | 一级页面名称，支持最小1个字符，最大8个字符。 | `葡萄` |
| `  └ name` | body | string | 是 | 一级页面名称，支持最小1个字符，最大8个字符。 | `水果` |
| `  └ rank` | body | mixed | 否 | 页面类目排序字段，在同级别优先级权重，越大则越靠前，可选范围[100000]，相同排序数字，创建时间最新的靠前排列。0排序在最后面，以此类推。 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/batchCreateCategory?app_key=your_appkey_here&method=shop.batchCreateCategory&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少页面id（sub_code: isv.missing-parameter:10003） | 请填写页面id |
| `40004` | 非法的参数 / 单次创建一级+二级分类总数超过限制（sub_code: isv.parameter-invalid:20162） | 请减少单次创建分类数 |
| `50002` | 业务处理失败 / 一级类目下分类总数（sub_code: isv.business-failed:20163） | 页面内一级分类总数最多100个 |

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
        "cid": "7352789789583868195",
        "level": "2",
        "msg": "rank值超出范围(0~100000)",
        "name": "葡萄",
        "parent_name": "水果"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:10003",
  "sub_msg": "缺少页面id"
}
```

## 备注
