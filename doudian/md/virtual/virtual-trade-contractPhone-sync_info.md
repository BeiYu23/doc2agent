# trade.contractPhone.sync_info

> 合约机办理结果同步接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.virtual.trade.contractPhone.sync_info` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/contractPhone/sync_info` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/2437 |
| 更新日期 | `2022-10-10` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 店铺单id | `1234` |
| `sku_order_id` | body | string | 是 | sku单id | `456868` |
| `phone_number` | body | string | 是 | 合约手机号码 | `1388888888` |
| `update_time` | body | number | 是 | 发生的时间（单位毫秒） | `12454545454` |
| `contract_result` | body | number | 是 | 1：合约待办理，2：合约办理中，3：合约办理成功，4：合约办理失败 | `1` |
| `remark` | body | string | 否 | 合约办理回传备注 | `办理完成` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trade/contractPhone/sync_info?app_key=your_appkey_here&method=trade.contractPhone.sync_info&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_biz` | object | 返回结构 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ret_biz": {
      "ret_code": "0",
      "ret_msg": "回传成功"
    }
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
