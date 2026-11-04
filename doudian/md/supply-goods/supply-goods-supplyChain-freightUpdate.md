# supplyChain.freightUpdate

> 运费模版变更

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.freightUpdate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/freightUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/7431 |
| 更新日期 | `2025-04-28` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `spu_id` | body | mixed | 否 | 分销品id | `70000000001` |
| `freight_id` | body | mixed | 否 | 运费模版id | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/freightUpdate?app_key=your_appkey_here&method=supplyChain.freightUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 错误码 | `0` |
| `msg` | string | 错误信息 | `分销品参数不正确` |

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
    "msg": "分销品参数不正确"
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
