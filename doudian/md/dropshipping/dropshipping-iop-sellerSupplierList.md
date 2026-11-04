# iop.sellerSupplierList

> 【商家】查询厂商管理列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dropshipping.iop.sellerSupplierList` |
| 中文名 | 【商家】查询厂商管理列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/sellerSupplierList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/1799 |
| 更新日期 | `2021-09-09` |

## 接口说明

- 文档书: 代发API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 是 | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |
| `page_size` | body | number | 是 | 返回数量，最大 100 | `20` |
| `bind_status` | body | array | 否 | 绑定状态（未知-0、待审核-1、已通过-2、已拒绝-3、已解绑-4） | `[1,2]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/sellerSupplierList?app_key=your_appkey_here&method=iop.sellerSupplierList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `supplier_shop_list` | array | 绑定列表 | `` |
| `page` | number | 返回页码，页码从 0 开始 PS：当前采用分页返回，数量和页数会一起传 | `0` |
| `page_size` | number | 返回数量，最大 100 | `20` |
| `total` | number | 总绑定数 | `100` |

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
    "supplier_shop_list": [
      {
        "apply_time": "1630484005",
        "band_time": "1630484005",
        "bind_status": "1",
        "refuse_time": "1630484005",
        "supplier_shop_id": "77977",
        "supplier_shop_name": "大白店铺二"
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
