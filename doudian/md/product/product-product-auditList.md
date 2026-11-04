# product.auditList

> 审核记录列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.auditList` |
| 中文名 | 审核记录列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/auditList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1748 |
| 更新日期 | `2025-01-07` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `publish_status` | body | mixed | 是 | 指定审核状态返回商品列表：0-审核中 1-审核通过 2-审核拒绝 | `0` |
| `page` | body | mixed | 是 | 第几页（第一页为0，最大为99） | `0` |
| `size` | body | mixed | 是 | 每页返回条数，最多支持100条 | `20` |
| `product_id` | body | mixed | 否 | 商品id | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/auditList?app_key=your_appkey_here&method=product.auditList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `records` | array | 审核记录列表 | `` |
| `total` | mixed | 总数量 | `11` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010001:系统异常,请重试（sub_code: isv.business-failed:2010001） | 请稍后重试 |
| `50002` | 业务处理失败 / 2010004:page or size is invalid（sub_code: isv.business-failed:2010004） | page or size is invalid |

## 响应示例

成功：

```json
{
  "data": {
    "records": [
      {
        "audit_reason": {},
        "audit_reason_details": [
          {
            "reject_reason_list": [
              {
                "reason_text": "驳回原因",
                "reject_img_list": [
                  {
                    "url": "url"
                  }
                ],
                "sku_infos": [
                  {
                    "sku_id": "skuid",
                    "sku_title": "规格名"
                  }
                ]
              }
            ],
            "title": "驳回模块名称",
            "type": "驳回模块类型"
          }
        ],
        "audit_time": "1668135600",
        "img_url": "http://aaa",
        "product_id": "111",
        "publish_status": "0",
        "publish_time": "1668135600",
        "title": "测试商品"
      }
    ],
    "total": "11"
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
  "sub_code": "isv.business-failed:2010001",
  "sub_msg": "2010001:系统异常,请重试"
}
```

## 备注
