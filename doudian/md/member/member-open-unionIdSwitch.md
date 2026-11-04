# open.unionIdSwitch

> 抖音unionId转换抖店会员unionId

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.open.unionIdSwitch` |
| 中文名 | 抖音unionId转换抖店会员unionId |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/unionIdSwitch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/4193 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `union_id` | body | string | 是 | 抖音unionId | `1111-2222-3333-4444` |
| `type` | body | mixed | 是 | 1-抖音unionId | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/unionIdSwitch?app_key=your_appkey_here&method=open.unionIdSwitch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `union_id` | string | 抖店会员unionId | `adfdafsd` |
| `type` | mixed | 2-代表抖店会员unionId | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 根据unionId查询用户信息失败，请检查unionId（sub_code: isv.business-failed:20010） | 检查请求参数 |
| `50002` | 业务处理失败 / 店铺查询满天星系统异常，请检查店铺是否已入驻满天星（sub_code: isv.business-failed:20011） | 检查请求参数 |
| `50002` | 业务处理失败 / 生成电商侧unionId失败，请检查参数（sub_code: isv.business-failed:20012） | 检查请求参数 |

## 响应示例

成功：

```json
{
  "data": {
    "type": "2",
    "union_id": "adfdafsd"
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
  "sub_code": "isv.business-failed:20010",
  "sub_msg": "根据unionId查询用户信息失败，请检查unionId"
}
```

## 备注
