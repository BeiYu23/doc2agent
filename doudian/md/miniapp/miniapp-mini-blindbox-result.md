# 小程序用户抽盒，同步抽盒结果平台

> mini.blindbox.result — 小程序用户抽盒，同步抽盒结果平台
1、使用场景说明，用户下单后在小程序抽完后把盲盒结果回传平台，商家可以再订单详情查看抽中结果，用户可以在订单详情查看抽中结果

| 元信息 | 值 |
| --- | --- |
| 中文名 | 小程序用户抽盒，同步抽盒结果平台 |
| 文档地址 | `/docs/doudian/miniapp/miniapp-mini-blindbox-result` |
| 接口 ID | `doudian.miniapp.mini.blindbox.result` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/blindbox/result` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6798 |
| 更新日期 | `2024-08-26` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 店铺单id | `777` |
| `douyin_open_id` | body | string | 是 | 抖音用户openId | `12341234123412` |
| `blind_box_result_list` | body | array | 是 | 奖品结果列表 | `` |
| `  └ sku_order_id` | body | string | 是 | sku单id | `777` |
| `  └ blind_result_img` | body | string | 是 | 盲盒结果图片 | `https://xxx/1.jpg` |
| `  └ blind_result_title` | body | string | 是 | 盲盒结果标题 | `LV包` |
| `  └ blind_result_sub_title` | body | string | 是 | 盲盒结果副标题 | `LV包黑色` |
| `  └ blind_result_open_time` | body | number | 是 | 盲盒结果开盒时间 | `1723631662789` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_success` | boolean | 是否写入成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 606000102:RPCError{PSM:[ecom.trade.order_query] Method:[GetSkuOrderInfoGroupsBySkuOrder] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110001] BizStatusMessage:[[FAIL,OQ10002,查询订单不存在]]}（sub_code: isv.business-failed:606000102） | 请找平台同学处理 |
| `50002` | 业务处理失败 / 606010000:入参店铺id非法（sub_code: isv.business-failed:606010000） | 请自行检查入参 |

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
  "sub_code": "isv.business-failed:606000102",
  "sub_msg": "606000102:RPCError{PSM:[ecom.trade.order_query] Method:[GetSkuOrderInfoGroupsBySkuOrder] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[110001] BizStatusMessage:[[FAIL,OQ10002,查询订单不存在]]}"
}
```

## 备注
