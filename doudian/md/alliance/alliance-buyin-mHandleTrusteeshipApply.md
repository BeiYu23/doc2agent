# buyin.mHandleTrusteeshipApply

> 团长托管商品审核

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.mHandleTrusteeshipApply` |
| 中文名 | 团长托管商品审核 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/mHandleTrusteeshipApply` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2138 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_ids` | body | array | 是 | 商品 id 列表，最多20个商品ID | `7843162348237` |
| `op_type` | body | string | 是 | 操作类型（1：通过，2：拒绝） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/mHandleTrusteeshipApply?app_key=your_appkey_here&method=buyin.mHandleTrusteeshipApply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fail_item` | string | 添加失败的记录（key：商品id，value：失败原因） | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 8192:当前托管商品数已达上限，无法新增托管商品（sub_code: isv.business-failed:8192） | 8192:当前托管商品数已达上限，无法新增托管商品 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_item": {}
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
