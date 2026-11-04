# address.delAftersaleAddress

> 删除商家地址库单条地址。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.address.delAftersaleAddress` |
| 中文名 | 删除商家地址库单条地址 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/delAftersaleAddress` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/7024 |
| 更新日期 | `2025-03-03` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `address_id` | body | mixed | 是 | 地址ID，通过/address/list获取到的地址信息对应的address_id字段 | `1356` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/delAftersaleAddress?app_key=your_appkey_here&method=address.delAftersaleAddress&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 请输入正确的参数（sub_code: isv.missing-parameter:4000） | 根据返回的错误信息修改参数后重试，如果多次重试后不成功，可以寻求抖店运营/开发同学协助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:6000） | 根据提示重试，如果多次重试或者等一段时间后重试没有结果，可以寻求抖店运营/开发同学协助。 |
| `50002` | 业务处理失败 / 操作过于频繁，请稍后重试（sub_code: isv.business-failed:100001） | 每个商家对地址库在1秒内只能操作1次，减低操作频率 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 根据提示重试，如果多次重试或者等一段时间后重试没有结果，可以寻求抖店运营/开发同学协助。 |
| `50002` | 业务处理失败 / 地址信息不存在（sub_code: isv.business-failed:100004） | 地址已经被删除或者传入的地址ID不存在 |
| `50002` | 业务处理失败 / 最后一条售后信息不可删除（sub_code: isv.business-failed:100018） | 停止删除，或者新增其他售后地址后重新尝试。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10003） | 根据提示重试，如果多次重试或者等一段时间后重试没有结果，可以寻求抖店运营/开发同学协助。 |
| `50002` | 业务处理失败 / 地址已删除，请刷新页面重试（sub_code: isv.business-failed:5004） | 地址已经被删除或者传入的地址ID不存在 |
| `50002` | 业务处理失败 / 当前店铺信息无权限访问（sub_code: isv.business-failed:10001） | 当前地址ID不属于当前登录店铺，改变地址ID或者登录店铺后重重试。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 根据提示重试，如果多次重试或者等一段时间后重试没有结果，可以寻求抖店运营/开发同学协助。 |
| `50002` | 业务处理失败 / 该地址为默认退货地址，请更换默认退货地址为其他地址后再删除（sub_code: isv.business-failed:100013） | 将默认退货地址设置为其他地址后重试 |
| `50002` | 业务处理失败 / 该地址为默认发货地址，请更换默认发货地址为其他地址后再删除（sub_code: isv.business-failed:100014） | 将默认发货地址设置为其他地址后重试 |
| `50002` | 业务处理失败 / 地址被XXX等XX个多地址退货策略使用，请更换其它地址后删除（sub_code: isv.business-failed:100016） | 解除地址策略和地址的绑定关系后重试。 |
| `50002` | 业务处理失败 / 代发发货正在使用该地址，请前往「抖店后台」-「发货中心」-「厂商代发」页面的设置按钮更换代发发货地址后再删除（sub_code: isv.business-failed:100017） | 按照错误返回信息处理后重试 |
| `50002` | 业务处理失败 / 该地址正用于电子面单订购，请新建地址或取消订购关系后删除（sub_code: isv.business-failed:100015） | 按照错误返回信息处理后重试 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:4000",
  "sub_msg": "请输入正确的参数"
}
```

## 备注
