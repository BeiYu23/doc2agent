# logistics.getProofRules

> 查询举证规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.getProofRules` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getProofRules` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8391 |
| 更新日期 | `2026-07-13` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `company` | body | string | 是 | 载体编码 | `ems` |
| `ticketType` | body | string | 否 | 三级工单类型码，多个以英文逗号拼接（例："11713,11714"），为空时返回所有 | `11501,11502` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getProofRules?app_key=your_appkey_here&method=logistics.getProofRules&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ext` | string | 预留扩展字段 | `""` |
| `rule_map` | string | key: 三级工单类型码 (typeCode), value: 该工单类型对应的规则结构 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40004） | 更新参数 |

## 响应示例

成功：

```json
{
  "data": {
    "ext": {},
    "rule_map": {}
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
  "sub_code": "isv.parameter-invalid:40004",
  "sub_msg": "参数错误"
}
```

## 备注
