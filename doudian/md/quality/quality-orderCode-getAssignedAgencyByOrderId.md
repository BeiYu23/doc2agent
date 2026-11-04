# orderCode.getAssignedAgencyByOrderId

> 通过订单号获取已分配的质检信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.quality.orderCode.getAssignedAgencyByOrderId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/orderCode/getAssignedAgencyByOrderId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1582/7400 |
| 更新日期 | `2025-04-11` |

## 接口说明

- 文档书: 质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `orderIds` | body | array | 是 | 店铺单号列表，最多支持50个店铺单号一起查询，超过50个取前50个店铺单 | `[     6941308530834610142,     6941334564693612510,     6941024859835733374   ]` |
| `shopId` | body | mixed | 是 | 店铺ID | `1111228346` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/orderCode/getAssignedAgencyByOrderId?app_key=your_appkey_here&method=orderCode.getAssignedAgencyByOrderId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_id` | mixed | 店铺ID | `1111228346` |
| `shop_name` | string | 店铺名称 | `订单测试店铺` |
| `order_agency_info` | array | 订单分配的质检机构信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 商家ID不能为空（sub_code: isv.missing-parameter:20001） | 填写店铺id |
| `50002` | 业务处理失败 / 查询店铺失败（sub_code: isv.business-failed:20002） | 稍后重试 |
| `40002` | 缺少必选参数 / 店铺单号不能为空（sub_code: isv.missing-parameter:20003） | 填写店铺单号 |
| `50002` | 业务处理失败 / 订单记录不存在（sub_code: isv.business-failed:20004） | 确认单号是否填写正确 |
| `50002` | 业务处理失败 / 当前商家不是ERP商家（sub_code: isv.business-failed:20005） | 检查店铺id填写是否正确 |
| `50002` | 业务处理失败 / 查询店铺单信息失败（sub_code: isv.business-failed:20006） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "order_agency_info": [
      {
        "order_id": "6917604403289457832",
        "quality_agency_id": "101",
        "quality_agency_name": "二手潮奢质检机构名称",
        "warehouse_code": "02",
        "warehouse_name": "二手潮奢质检仓名称"
      }
    ],
    "shop_id": "1111228346",
    "shop_name": "订单测试店铺"
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
  "sub_code": "isv.missing-parameter:20001",
  "sub_msg": "商家ID不能为空"
}
```

## 备注
