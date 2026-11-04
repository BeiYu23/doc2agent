# 物流商推送商家的产品类型/增值服务的变更数据

> logistics.pushOnlineService — 物流商推送商家的产品类型/增值服务的变更数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 物流商推送商家的产品类型/增值服务的变更数据 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-pushOnlineService` |
| 接口 ID | `doudian.logistics-provider.logistics.pushOnlineService` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushOnlineService` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8368 |
| 更新日期 | `2026-06-29` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `netsite` | body | object | 是 | 月结账号或者网点编码  shopId+网点编码或者月结账号确定唯一 | `` |
| `  └ secret_key` | body | string | 否 | 总对总时的密码 | `1` |
| `  └ net_code` | body | string | 否 | 网点编码,当类型字段为加盟制时，则该字段为必填；直营制时无需使用 | `1` |
| `  └ category` | body | string | 是 | 物流服务商类型（直营or加盟） | `"加盟"` |
| `  └ monthly_account` | body | string | 否 | 月结账号，当类型字段为直营制时，则该字段会用到，加盟制时无需使用； 总对总时的账号 | `1` |
| `  └ verification_code` | body | string | 否 | 验证码 | `1` |
| `service_list` | body | array | 否 | 增值服务 | `` |
| `  └ service_code` | body | string | 否 | 物流产品编码 | `1` |
| `  └ refuse_reason` | body | string | 否 | statusType=3 时必填，拒绝原因 | `1` |
| `  └ status_type` | body | mixed | 否 | 0=已开通 1=未开通 2=审核中 3=拒绝 | `1` |
| `product_list` | body | array | 否 | 物流产品 | `` |
| `  └ service_code` | body | string | 否 | 物流产品编码 | `1` |
| `  └ status_type` | body | mixed | 否 | 0=已开通 1=未开通 2=审核中 3=拒绝 | `1` |
| `  └ refuse_reason` | body | string | 否 | statusType=3 时必填，拒绝原因 | `1` |
| `op_timestamp` | body | mixed | 是 | 时间戳 | `1` |
| `sign_mode` | body | mixed | 否 | 合作模式 | `1` |
| `op_source` | body | mixed | 否 | 开通来源 | `1` |
| `shop_id_compatible` | body | mixed | 是 | 商家id | `1` |
| `sub_brand` | body | string | 是 | 实际的物流商code | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/pushOnlineService?app_key=your_appkey_here&method=logistics.pushOnlineService&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `invalid_service_list` | array | 无效增值服务列表 | `` |
| `invalid_product_list` | array | 无效物流产品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 存在非法参数（sub_code: isv.parameter-invalid:4006） | 检查参数是否正确 |
| `50002` | 业务处理失败 / 面单账户不存在（sub_code: isv.business-failed:14023） | 检查参数是否正确 |
| `40004` | 非法的参数 / 产品/增值服务编码无效（sub_code: isv.parameter-invalid:4056） | 检查参数是否正确 |

## 响应示例

成功：

```json
{
  "data": {
    "invalid_product_list": [
      {
        "refuse_reason": "1",
        "service_code": "1",
        "status_type": "1"
      }
    ],
    "invalid_service_list": [
      {
        "refuse_reason": "1",
        "service_code": "1",
        "status_type": "1"
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
  "sub_code": "isv.parameter-invalid:4006",
  "sub_msg": "存在非法参数"
}
```

## 备注
