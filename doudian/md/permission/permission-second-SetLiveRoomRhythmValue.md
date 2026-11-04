# 设置主播节奏大师阈值

> second.SetLiveRoomRhythmValue — 设置主播节奏大师阈值

| 元信息 | 值 |
| --- | --- |
| 中文名 | 设置主播节奏大师阈值 |
| 文档地址 | `/docs/doudian/permission/permission-second-SetLiveRoomRhythmValue` |
| 接口 ID | `doudian.permission.second.SetLiveRoomRhythmValue` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/SetLiveRoomRhythmValue` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1506/7916 |
| 更新日期 | `2025-12-02` |

## 接口说明

- 文档书: 二方开放权限组（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `anchor_id` | body | string | 否 | 主播ID | `test` |
| `type` | body | string | 否 | 阈值类型 | `price_offer` |
| `value` | body | string | 否 | 阈值数值 | `12.3` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/SetLiveRoomRhythmValue?app_key=your_appkey_here&method=second.SetLiveRoomRhythmValue&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
