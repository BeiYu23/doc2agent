# buyin.activityProductCancel

> 一级团长取消活动提报申请接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.activityProductCancel` |
| 中文名 | 一级团长取消活动提报申请 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/activityProductCancel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1927 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | number | 是 | 活动 id | `54321` |
| `product_id` | body | number | 是 | 商品 id | `174913561741412435` |
| `origin_activity_id` | body | number | 否 | 原始活动 id | `375162` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/activityProductCancel?app_key=your_appkey_here&method=buyin.activityProductCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 操作结果（true：操作成功） | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 8192:已经取消的商品无需再次取消（sub_code: isv.business-failed:8192） | 8192:已经取消的商品无需再次取消 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isv.business-failed:4197",
  "sub_msg": "需【招商团长】角色授权后访问"
}
```

## 备注
