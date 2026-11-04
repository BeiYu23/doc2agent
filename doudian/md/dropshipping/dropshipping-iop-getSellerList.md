# iop.getSellerList

> 【厂家】查询商家列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.getSellerList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/getSellerList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/1752 |
| 更新日期 | `2022-04-06` |

## 接口说明

- 文档书: 代发API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 否 | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |
| `page_size` | body | number | 否 | 返回数量，最大 100 | `20` |
| `bind_status` | body | array | 否 | 绑定状态（未知-0、申请绑定待审核-1、已通过-2、已拒绝-3、已解绑-4、申请解绑待审核-5） | `[1,2]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/getSellerList?app_key=your_appkey_here&method=iop.getSellerList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `seller_shop_list` | array | 绑定列表 | `` |
| `page_size` | number | 返回数量，最大 100 | `20` |
| `total` | number | 总绑定数 | `100` |
| `page` | number | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "0",
    "page_size": "20",
    "seller_shop_list": [
      {
        "apply_time": "1630484005",
        "band_time": "1630484005",
        "bind_status": "1",
        "refuse_time": "1630484005",
        "seller_shop_id": "1111",
        "seller_shop_name": "大白店铺"
      }
    ],
    "total": "100"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
