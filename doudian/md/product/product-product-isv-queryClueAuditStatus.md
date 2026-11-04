# product.isv.queryClueAuditStatus

> 查询线索提报审核结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.isv.queryClueAuditStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isv/queryClueAuditStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2148 |
| 更新日期 | `2024-04-02` |

## 接口说明

- 文档书: 商品API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_id` | body | mixed | 是 | 线索id | `1` |
| `item_id` | body | mixed | 是 | 商品id | `1` |
| `page` | body | object | 是 | 分页参数 | `` |
| `  └ current` | body | mixed | 是 | 页码，从1开始 | `1` |
| `  └ page_size` | body | mixed | 是 | 页大小，不要超过500 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/isv/queryClueAuditStatus?app_key=your_appkey_here&method=product.isv.queryClueAuditStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 提报记录列表 | `` |
| `total` | mixed | 总记录数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 提报记录不存在（sub_code: isv.business-failed:501） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "audit_status": "1",
        "pic_url": "http://xxxx.image",
        "product_id": "1",
        "product_name": "长裤",
        "refused_reason": "无",
        "shop_id": "1",
        "shop_name": "1",
        "submit_id": "1",
        "submit_time": "0"
      }
    ],
    "total": "10"
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
  "sub_code": "isv.business-failed:501",
  "sub_msg": "提报记录不存在"
}
```

## 备注
