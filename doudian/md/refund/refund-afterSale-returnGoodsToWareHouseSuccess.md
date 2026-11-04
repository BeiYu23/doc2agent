# afterSale.returnGoodsToWareHouseSuccess

> 商家确认售后单对应的用户退货入仓成功

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.returnGoodsToWareHouseSuccess` |
| 中文名 | 商家确认售后单对应的用户退货入仓成功 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/returnGoodsToWareHouseSuccess` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/815 |
| 更新日期 | `2021-08-11` |

## 接口说明

- 文档书: 售后退款API（版本 V6.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | string | 是 | 售后单Id | `12345` |
| `op_time` | body | number | 是 | 商家确认退货入仓时间，Unix时间戳，时间为秒 | `1627905819` |
| `tracking_no` | body | string | 否 | 用户退货物流单号 | `SF12334` |
| `logistics_company_code` | body | string | 否 | 物流公司代号 | `shunfeng` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/returnGoodsToWareHouseSuccess?app_key=your_appkey_here&method=afterSale.returnGoodsToWareHouseSuccess&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 序列化错误（sub_code: isv.parameter-invalid:11004） | 通常为入参问题，请检查后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:10002） | 通常为严重的系统错误问题，请检查并谨慎重试。 |
| `50002` | 业务处理失败 / 系统错误，请重试（sub_code: isv.business-failed:10000） | 通常为超时，请检查后重试 |
| `50002` | 业务处理失败 / 售后单类型与策略限制不符合，未命中此策略（sub_code: isv.business-failed:12001） | 检查后重试 |
| `50002` | 业务处理失败 / 店铺未设置或启用售后小助手策略，请店铺通过抖店后台或以下链接进行设置：https://fxg.jinritemai.YOUR_SECRET_KEY（sub_code: isv.business-failed:11002） | 检查小助手是否开启 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:11000） | 通常为入参错误，请检查 |
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:11004",
  "sub_msg": "序列化错误"
}
```

## 备注
