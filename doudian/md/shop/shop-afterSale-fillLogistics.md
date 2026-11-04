# afterSale.fillLogistics

> 售后商家发货

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.afterSale.fillLogistics` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/fillLogistics` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2068 |
| 更新日期 | `2022-06-27` |

## 接口说明

- 文档书: 店铺API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 是 | 售后单ID | `7085126861562380588` |
| `send_type` | body | string | 是 | 发货类型，目前仅支持补寄(1) | `1` |
| `company_code` | body | string | 是 | 物流公司编号 | `yuantong` |
| `tracking_no` | body | string | 是 | 物流单号 | `YT1231231231` |
| `book_time_begin` | body | number | 否 | 预约上门取货时间戳-目前只超市用 | `1655955000` |
| `book_time_end` | body | number | 否 | 预约上门取货时间戳-目前只超市用 | `1655955600` |
| `store_id` | body | number | 否 | 门店ID | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/fillLogistics?app_key=your_appkey_here&method=afterSale.fillLogistics&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 12000:物流信息校验失败（sub_code: isv.business-failed:12000） | 填入有效物流信息 |
| `50002` | 业务处理失败 / 物流信息校验失败（sub_code: isv.business-failed:602001） | 填入有效物流信息 |
| `20000` | 系统错误 / 网络异常稍后重试（sub_code: isp.service-error:10000） | 重试 |
| `20000` | 系统错误 / 网络异常稍后重试（sub_code: isp.service-error:10002） | 重试 |
| `50002` | 业务处理失败 / 物流信息校验失败（sub_code: isv.business-failed:50002） | 填入有效物流信息 |
| `50002` | 业务处理失败 / 无效售后单（sub_code: isv.business-failed:11000） | 请检查售后单信息 |

## 响应示例

成功：

```json
{
  "err_no": 0,
  "message": "success",
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
  "sub_code": "isv.business-failed:12000",
  "sub_msg": "12000:物流信息校验失败"
}
```

## 备注
