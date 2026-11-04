# 查询品牌列表

> supplyChain.queryBrandList — 查询品牌列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询品牌列表 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-supplyChain-queryBrandList` |
| 接口 ID | `doudian.cross-border.supplyChain.queryBrandList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryBrandList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6324 |
| 更新日期 | `2024-03-26` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | mixed | 是 | 当前页码 | `1` |
| `page_size` | body | mixed | 是 | 每页数量 | `10` |
| `category_id` | body | mixed | 是 | 类目id | `20004` |
| `bmp_code` | body | string | 是 | 业务身份 | `xiaodian.crossborder` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/queryBrandList?app_key=your_appkey_here&method=supplyChain.queryBrandList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_list` | array | 返回值 | `` |
| `page` | mixed | 当前页码 | `1` |
| `page_size` | mixed | 每页数量 | `10` |
| `total` | mixed | 当前页返回数量 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:400001） | 请检查传入的参数 |
| `50002` | 业务处理失败 / 内部服务返回错误（sub_code: isv.business-failed:200001） | 请检查传入的参数并稍后重试 |
| `40004` | 非法的参数 / 分页不允许超过100（sub_code: isv.parameter-invalid:2002） | 请检查传入的参数 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_list": [
      {
        "brand_id": "80855074",
        "brand_name": "雅诗兰黛",
        "brand_name_cn": "雅诗兰黛",
        "brand_name_en": "ESTEE LAUDER"
      }
    ],
    "page": "1",
    "page_size": "10",
    "total": "10"
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
  "sub_code": "isv.parameter-invalid:400001",
  "sub_msg": "非法的参数"
}
```

## 备注
