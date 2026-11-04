# order.review

> 商家回传订单审核结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.order.review` |
| 中文名 | 商家回传订单审核结果 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/review` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/1785 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 订单API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_type` | body | number | 是 | 表示订单审核的类型 3001 通信卡审核 | `3001` |
| `reject_code` | body | number | 是 | 0 审核通过  200001 下单身份信息180天内重复下单 200002 超过下单身份信息可办理数量 200003 下单身份信息年龄不符合要求  200004 下单地址为运营商禁售地区  200005 未通过运营商审核，具体可联系商家 200006 地址模糊无法发货 | `0` |
| `object_id` | body | string | 是 | 审核的单id取决于什么审核 通信卡审核 店铺单id | `4921300864966120582` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 20002:参数错误:找不到订单的审核任务（sub_code: isv.business-failed:20002） | 修改入参 |
| `50002` | 业务处理失败 / 20003:调用交易失败（sub_code: isv.business-failed:20003） | 请检查请求参数 |

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
  "sub_code": "isv.business-failed:20002",
  "sub_msg": "20002:参数错误:找不到订单的审核任务"
}
```

## 备注
