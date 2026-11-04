# supplyCenter.base.brand

> 精选货源获取类目品牌

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.base.brand` |
| 中文名 | 精选货源获取类目品牌 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyCenter/base/brand` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5328 |
| 更新日期 | `2023-10-25` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 是 | 类目id | `123` |
| `query` | body | string | 否 | 品牌前缀（中文或者英文），适用于不需要品牌资质的场景，根据前缀搜索品牌 | `wu` |
| `brand_ids` | body | array | 否 | （选填）品牌ids，传了品牌ids默认直接拿品牌id搜索并返回结果(放在brand_list里)，不会使用其他入参 | `[123]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.base.brand&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_list` | array | 品牌列表，无关乎授权 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照品牌接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/14/1267 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_list": [
      {
        "brand_id": "123",
        "name_cn": "中文名",
        "name_en": "xxxx"
      }
    ]
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
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照品牌接口"
}
```

## 备注
