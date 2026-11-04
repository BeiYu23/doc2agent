# mini.blindbox.merchantresult

> 1、使用场景说明，主播在直播间抽完后把盲盒结果回传平台，商家可以再订单详情查看抽中结果，用户可以在订单详情查看抽中结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.mini.blindbox.merchantresult` |
| 中文名 | 主播在直播间抽完后把盲盒结果回传平台 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/blindbox/merchantresult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7436 |
| 更新日期 | `2025-04-29` |

## 接口说明

- 文档书: 工具API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `blind_box_result_list` | body | array | 是 | 盲盒信息列表 | `` |
| `  └ sku_order_id` | body | string | 是 | sku单id | `777` |
| `  └ blind_result_img` | body | string | 是 | 盲盒结果图片 | `https://xxx/1.jpg` |
| `  └ blind_result_title` | body | string | 是 | 盲盒结果标题 | `LV包` |
| `  └ blind_result_sub_title` | body | string | 是 | 盲盒信息备注字段，开发者自定义 | `45671-3` |
| `  └ blind_result_open_time` | body | number | 是 | 盲盒结果开盒时间 | `1723631662789` |
| `doudian_open_id` | body | string | 是 | 抖店openid | `31341#1A123` |
| `shop_order_id` | body | string | 是 | 店铺单id | `777` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/applyActivities?app_key=your_appkey_here&method=buyin.applyActivities&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_success` | boolean | 写入成功/失败 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 606000102:RPCError{PSM:[ecom.trade.order_query] Method:[GetSkuOrderInfoGroupsBySkuOrder] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110001] BizStatusMessage:[[FAIL,OQ10002,查询订单不存在]]}（sub_code: isv.business-failed:606000102） | 找平台同学 |
| `50002` | 业务处理失败 / 606010000:入参店铺id非法（sub_code: isv.business-failed:606010000） | 检查入参 |

## 响应示例

成功：

```json
{
  "data": {
    "result": [
      {
        "error_code": "0",
        "error_msg": "success",
        "is_success": "true",
        "product_id": "123123123123"
      }
    ],
    "total": "20"
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
  "sub_code": "isv.business-failed:606000102",
  "sub_msg": "606000102:RPCError{PSM:[ecom.trade.order_query] Method:[GetSkuOrderInfoGroupsBySkuOrder] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110001] BizStatusMessage:[[FAIL,OQ10002,查询订单不存在]]}"
}
```

## 备注
