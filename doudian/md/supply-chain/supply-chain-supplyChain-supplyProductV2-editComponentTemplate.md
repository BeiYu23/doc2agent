# 编辑尺码模板

> supplyChain.supplyProductV2.editComponentTemplate — 编辑尺码模板

| 元信息 | 值 |
| --- | --- |
| 中文名 | 编辑尺码模板 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-supplyProductV2-editComponentTemplate` |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.editComponentTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6674 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | mixed | 否 | 模板id | `1` |
| `template_name` | body | string | 否 | 模板名称 | `1` |
| `component_front_data` | body | string | 否 | 商品组件编辑器源数据 json | `1` |
| `component_data` | body | string | 否 | 商品组件数据 json | `1` |
| `image` | body | object | 否 | image信息 | `` |
| `  └ url` | body | string | 否 | url | `` |
| `  └ width` | body | mixed | 否 | 宽 | `` |
| `  └ height` | body | mixed | 否 | 高 | `` |
| `  └ source` | body | string | 否 | 来源 | `` |
| `shareable` | body | boolean | 否 | 是否可共享 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProductV2.editComponentTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed |  | `` |
| `msg` | string |  | `` |
| `success` | boolean |  | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "",
    "success": "0"
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
