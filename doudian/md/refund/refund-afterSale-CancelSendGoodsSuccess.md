# afterSale.CancelSendGoodsSuccess

> 1、商家在抖店后台售后小助手配置取消发货自动退策略；
2、当用户发起退款申请，且商家判断符合退款的场景时，可以调用取消发货接口同步平台取消发货；
3、命中策略后该售后单自动执行退款操作；

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.CancelSendGoodsSuccess` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/CancelSendGoodsSuccess` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/816 |
| 更新日期 | `2021-08-11` |

## 接口说明

- 文档书: 售后退款API（版本 V5.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | string | 是 | 售后单ID | `12345` |
| `op_time` | body | number | 是 | unix时间戳，单位为秒 | `1627905819` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/CancelSendGoodsSuccess?app_key=your_appkey_here&method=afterSale.CancelSendGoodsSuccess&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 序列化失败，可能为入参问题，请检查。（sub_code: isv.business-failed:11004） | 检查后重试 |
| `20000` | 系统错误 / 参数错误（sub_code: isp.service-error:10002） | 通常为不应该发生的系统错误，请检查售后单状态，谨慎重试 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:11000） | 请检查入参 |
| `50002` | 业务处理失败 / 系统错误（sub_code: isv.business-failed:10000） | 可能为系统处理超时，请检查后重试 |
| `50002` | 业务处理失败 / 店铺未设置或启用售后小助手策略，请店铺通过抖店后台或以下链接进行设置：https://fxg.jinritemai.YOUR_SECRET_KEY（sub_code: isv.business-failed:11002） | 检查是否开启小助手策略 |
| `50002` | 业务处理失败 / 售后单已被其他自动退款方式命中,售后小助手策略不再执行（sub_code: isv.business-failed:12001） | 查看售后单状态 |
| `50002` | 业务处理失败 / 该售后单不存在（sub_code: isv.business-failed:11003） | 检查入参后重试 |
| `50002` | 业务处理失败 / 获取售后小助手策略失败（sub_code: isv.business-failed:12000） | 请检查后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:11004",
  "sub_msg": "序列化失败，可能为入参问题，请检查。"
}
```

## 备注
