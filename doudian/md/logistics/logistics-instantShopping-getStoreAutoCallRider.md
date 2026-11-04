# instantShopping.getStoreAutoCallRider

> 查询自动呼叫运力配置

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.instantShopping.getStoreAutoCallRider` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/7189 |
| 更新日期 | `2025-01-02` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 商家的门店编号 | `55106601` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.getStoreAutoCallRider&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `autocall_info` | object | 自动呼叫设置信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 店铺ID不能为空（sub_code: isv.missing-parameter:40011） | 店铺ID不能为空 |
| `40002` | 缺少必选参数 / 门店ID不能为空（sub_code: isv.missing-parameter:40012） | 门店ID不能为空 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20201） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / store_id不存在/错误（sub_code: isv.business-failed:50114） | 无需填写 |
| `50002` | 业务处理失败 / 系统错误，请稍后重试（sub_code: isv.business-failed:20112） | 无需填写 |

## 响应示例

成功：

```json
{
  "data": {
    "autocall_info": {
      "delay_time": "5",
      "service_status": "1",
      "service_type": "1"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:40011",
  "sub_msg": "店铺ID不能为空"
}
```

## 备注
