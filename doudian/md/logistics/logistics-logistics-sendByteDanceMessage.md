# logistics.sendByteDanceMessage

> 短信代发

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.sendByteDanceMessage` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/sendByteDanceMessage` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2462 |
| 更新日期 | `2024-02-21` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybillCode` | body | string | 是 | 运单号 | `75538750081658` |
| `expressCompany` | body | string | 是 | 快递商编码 | `zhongtong` |
| `message` | body | string | 是 | 代码内容 | `【妈妈驿站】取货码02-124，您有中通快递包裹，已到您的快递已到达圆通妈妈驿站` |
| `pickMsgCode` | body | string | 是 | 取件消息唯一编码 | `0A0729AE8E3A49C2FAAE07949B972AB6` |
| `scene` | body | string | 否 | 业务场景（与平台研发确认具体值） | `default` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/sendByteDanceMessage?app_key=your_appkey_here&method=logistics.sendByteDanceMessage&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 修改参数 |
| `50002` | 业务处理失败 / 数据库错误（sub_code: isv.business-failed:11001） | 下个字节单 |
| `50002` | 业务处理失败 / 不是字节包裹（sub_code: isv.business-failed:10014） | 找测试下个字节单 |
| `50002` | 业务处理失败 / 关联下游处理失败（sub_code: isv.business-failed:11004） | 找研发确认问题 |
| `50002` | 业务处理失败 / 不是字节面单（sub_code: isv.business-failed:10015） | 找测试下个字节单 |
| `50002` | 业务处理失败 / 短信代发失败（sub_code: isv.business-failed:11010） | 找研发确认问题 |
| `50002` | 业务处理失败 / 内部处理失败（sub_code: isv.business-failed:11008） | 找研发确认问题 |
| `50002` | 业务处理失败 / 内容检测失败（sub_code: isv.business-failed:10002） | 换个合法短信内容 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误"
}
```

## 备注
