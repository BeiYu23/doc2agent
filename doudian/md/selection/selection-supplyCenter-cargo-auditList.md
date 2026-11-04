# 审核记录列表

> supplyCenter.cargo.auditList — 审核记录列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 审核记录列表 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-cargo-auditList` |
| 接口 ID | `doudian.selection.supplyCenter.cargo.auditList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5141 |
| 更新日期 | `2023-10-19` |

## 接口说明

- 文档书: 精选货源API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `publish_status` | body | number | 是 | 指定审核状态返回商品列表：0-审核中 1-审核通过 2-审核拒绝 | `0` |
| `page` | body | number | 是 | 第几页（第一页为0，最大为99） | `0` |
| `size` | body | number | 是 | 每页返回条数，最多支持100条 | `20` |
| `product_id` | body | number | 否 | 商品id | `11` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.auditList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `records` | array | 审核记录列表 | `` |
| `total` | number | 总数量 | `11` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品审核记录列表接口（sub_code: isv.parameter-invalid:6666） | https://op.jinritemai.com/docs/api-docs/14/1748 |

## 响应示例

成功：

```json
{
  "data": {
    "records": [
      {
        "audit_reason": {},
        "audit_time": "1668135600",
        "img_url": "http://aaa",
        "product_id": "1111",
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:6666",
  "sub_msg": "参照商品审核记录列表接口"
}
```

## 备注
