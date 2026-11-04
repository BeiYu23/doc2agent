# afterSale.rejectReasonCodeList

> 使用场景：
1、不传aftersale_id查询抖店支持的全量拒绝原因列表
2、传aftersale_id，商家查询该笔售后单可选的拒绝原因列表，注意：仅支持已发货的售后查询，备货中未发货订单返回为空。
3、如返回为空,有如下场景：
1)该售后单已完结或已

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.afterSale.rejectReasonCodeList` |
| 中文名 | 不传aftersale_id查询抖店支持的全量… |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/afterSale/rejectReasonCodeList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/1540 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 售后退款API（版本 V4.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_id` | body | number | 否 | 传入售后单id时，返回该笔售后单可选择的拒绝原因列表；仅支持已发货的售后查询，备货中未发货订单返回为空。 | `7140522277954699533` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/afterSale/rejectReasonCodeList?app_key=your_appkey_here&method=afterSale.rejectReasonCodeList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 售后商家拒绝原因详情列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000:系统错误，请重试（sub_code: isv.business-failed:10000） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "evidence_description": "请提供发货物流进度截图",
        "evidence_need": "Y",
        "image": "/obj/ecom-aftersale-image-example/vsfguUuWBsXzjgyexWJRoBUMVORQBnmvMQHBRFom.png",
        "order_type": "1",
        "pkg": "1",
        "reason": "多拍/错拍/不想要",
        "reject_reason_code": "1"
      }
    ]
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "10000:系统错误，请重试"
}
```

## 备注
