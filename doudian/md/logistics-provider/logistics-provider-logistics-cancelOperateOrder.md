# logistics.cancelOperateOrder

> 物流商取消单据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.cancelOperateOrder` |
| 中文名 | 物流商取消单据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/cancelOperateOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/4456 |
| 更新日期 | `2023-09-14` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 是 | 运单号 | `SF1234567890` |
| `reason` | body | string | 是 | 取消原因编码，枚举映射如下： 10800：空号错号 10801：无人接听、停关机（联系不上用户 10802：物品不符合寄件标准 10804：包裹破损、包裹不齐 10805：快递误操作 10806：客户无法提供身份证明 10807：违禁品 10808：寄件人超时未准备好货物 10809：收件地址不详 10810：扫描操作错误 10811：客户重复下单 10812：下错单 10813：揽收时间无法达成一致 10816：疫情导致快递员被隔离无法上门取 | `10800` |
| `status` | body | string | 是 | 取消 | `CANCELED` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/cancelOperateOrder?app_key=your_appkey_here&method=logistics.cancelOperateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | boolean | 请求结果（成功-true;失败-false） | `true` |
| `return_code` | string | 错误编码 | `1000` |
| `message` | string | 失败原因 | `服务端异常` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:12702） | 根据错误信息检查请求参数 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:12704） | 联系平台开发定位 |
| `50002` | 业务处理失败 / 实操单不存在（sub_code: isv.business-failed:12703） | 联系平台开发定位 |
| `50002` | 业务处理失败 / 当前状态已取消不允许更新（sub_code: isv.business-failed:12714） | 当前状态已取消不允许更新 |
| `50002` | 业务处理失败 / 当前状态不允许变更（sub_code: isv.business-failed:12710） | 当前状态不允许取消 |

## 响应示例

成功：

```json
{
  "data": {
    "message": "服务端异常",
    "result": "true",
    "return_code": "1000"
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
  "sub_code": "isv.parameter-invalid:12702",
  "sub_msg": "参数错误"
}
```

## 备注
