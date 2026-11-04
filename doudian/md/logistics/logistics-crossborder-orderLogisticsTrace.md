# crossborder.orderLogisticsTrace

> 服务商回传国际干线作业节点

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.crossborder.orderLogisticsTrace` |
| 中文名 | 服务商回传国际干线作业节点 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/orderLogisticsTrace` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/528 |
| 更新日期 | `2021-05-18` |

## 接口说明

- 文档书: 物流发货API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 字节电商平台的交易订单号 | `4789910161734698899` |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `QS` |
| `status` | body | number | 是 | 国际物流状态：1干线提货完成  2干线发运完成  3实物到港 | `1` |
| `occurrence_time` | body | string | 是 | 物流状态的真实发生时间，yyyy-MM-dd hh:mi:ss | `2020-03-21 11:22:33` |
| `origin` | body | string | 是 | 始发地（国/港口） | `505` |
| `destination` | body | string | 是 | 目的地（国/港口） | `505` |
| `transportation` | body | object | 否 | 国际物流信息（【干线发运完成】状态时，必须提供） | `-` |
| `  └ oversea_trans_no` | body | string | 否 | 国际运单号（CC/UPU）"一单到底"该单号同国内运单号 | `12345` |
| `  └ bill_no` | body | string | 否 | 提单号（BC） | `12345` |
| `  └ voyage_no` | body | string | 否 | 航司航班班次号（BC） | `12346` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/orderLogisticsTrace?app_key=your_appkey_here&method=crossborder.orderLogisticsTrace&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 1005:接口调用异常，请重试，多次失败请人工反馈（sub_code: isp.service-error:1005） | 调用方重试，多次重试失败请联系运营人员 |
| `50002` | 业务处理失败 / 1002:【干线发运完成】时,transportation信息overseaTransNo\|billNo不能缺失！（sub_code: isv.business-failed:1002） | 请根据提示回传正确的参数 |
| `50002` | 业务处理失败 / 1000:节点时序状态有误（sub_code: isv.business-failed:1000） | 请检查节点时序状态 |
| `50002` | 业务处理失败 / 1004:当前状态节点的时间不能早于平台推单成功时间、不能早于上一个状态操作时间，不能晚于系统当前时间（sub_code: isv.business-failed:1004） | 请检查当前状态节点的时间参数 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1005",
  "sub_msg": "1005:接口调用异常，请重试，多次失败请人工反馈"
}
```

## 备注
