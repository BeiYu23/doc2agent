# 批量解析团长活动推广链接

> buyin.colonelMultiParseActivityUrl — 批量解析团长活动推广链接

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量解析团长活动推广链接 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-colonelMultiParseActivityUrl` |
| 接口 ID | `doudian.alliance.buyin.colonelMultiParseActivityUrl` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonelMultiParseActivityUrl` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2429 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_url` | body | array | 是 | 活动商品链接列表，最多20个 | `["https://haohuo.jinritemai.com/views/product/detail?id=3566195499839129569&ins_activity_param=eNkdXXR"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/colonelMultiParseActivityUrl?app_key=your_appkey_here&method=buyin.colonelMultiParseActivityUrl&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `results` | string | 结果集，key：活动商品链接，value:链接信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "results": {}
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
  "sub_code": "isv.business-failed:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
