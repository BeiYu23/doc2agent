# second.liveroom.upsertAnchorBindRelationship

> 【三方接口】更新应用绑定的直播间主播列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.permission.second.liveroom.upsertAnchorBindRelationship` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/7472 |
| 更新日期 | `2025-05-20` |

## 接口说明

- 文档书: 二方开放权限组（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bind_type` | body | mixed | 是 | 主播与店铺绑定类型: 1人店一体号 2渠道号 | `1` |
| `anchor_login_name` | body | string | 否 | 主播抖音号 | `test` |
| `anchor_uid` | body | mixed | 否 | 主播uid。anchor_uid与anchor_login_name选填其一即可，不可同时为空 | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.liveroom.upsertAnchorBindRelationship&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `encrypt_uid` | string | 加密后的主播ID | `test` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:10010） | 检查接口入参 |

## 响应示例

成功：

```json
{
  "data": {
    "encrypt_uid": "test"
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
  "sub_code": "isv.parameter-invalid:10010",
  "sub_msg": "参数非法"
}
```

## 备注
