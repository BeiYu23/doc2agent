# brand.list

> 根据类目id获取可选品牌

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.brand.list` |
| 中文名 | 根据类目id获取可选品牌 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/brand/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1267 |
| 更新日期 | `2023-05-30` |

## 接口说明

- 文档书: 商品API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `categories` | body | array | 否 | （已停止使用）类目列表 | `[123]` |
| `offset` | body | number | 否 | （已停止使用）起始位 | `0` |
| `size` | body | number | 否 | （已停止使用）单次最大条数 | `10` |
| `sort` | body | string | 否 | （已停止使用）排序顺序，默认为倒排 0:降序, 1:升序 | `0` |
| `status` | body | string | 否 | （已停止使用）品牌状态 1:审核中, 2:审核通过, 3:审核拒绝 | `2` |
| `full_brand_info` | body | boolean | 否 | （已停止使用）是否返回完全的品牌信息 | `true` |
| `category_id` | body | number | 否 | （推荐使用，必填）类目id | `123` |
| `query` | body | string | 否 | 品牌前缀（中文或者英文），适用于不需要品牌资质的场景，根据前缀搜索品牌 | `wu` |
| `brand_ids` | body | array | 否 | （选填）品牌ids，传了品牌ids默认直接拿品牌id搜索并返回结果(放在brand_list里)，不会使用其他入参 | `[123]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/brand/list?app_key=your_appkey_here&method=brand.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_ids` | array | （已停止使用）品牌id列表 | `[]` |
| `brand_infos` | string | （已停止使用）品牌信息 | `` |
| `total` | number | （已停止使用）总数 | `0` |
| `has_more` | boolean | （已停止使用）还有更多 | `True` |
| `auth_required` | boolean | 类目是否要求品牌有授权 | `true` |
| `auth_brand_list` | array | 授权的品牌列表 | `` |
| `brand_list` | array | 未授权的品牌列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数category_id缺失（sub_code: isv.parameter-invalid:2010004） | 请检查是否输入了category_id参数 |
| `20000` | 系统错误 / 查询数据失败，系统异常（sub_code: isp.service-error:2010001） | 请重试 |
| `50002` | 业务处理失败 / 2010013:获取账号信息失败（sub_code: isv.business-failed:2010013） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "auth_brand_list": [
      {
        "brand_id": "123",
        "name_cn": "中文名",
        "name_en": "xxx"
      }
    ],
    "auth_required": "true",
    "brand_ids": "[]",
    "brand_infos": {},
    "brand_list": [
      {
        "brand_id": "123",
        "name_cn": "中文名",
        "name_en": "xxx"
      }
    ],
    "has_more": "True",
    "total": "0"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2010004",
  "sub_msg": "参数category_id缺失"
}
```

## 备注
