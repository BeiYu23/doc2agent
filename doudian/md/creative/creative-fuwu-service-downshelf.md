# 下架服务市场服务

> fuwu.service.downshelf — 下架服务市场服务接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 下架服务市场服务 |
| 文档地址 | `/docs/doudian/creative/creative-fuwu-service-downshelf` |
| 接口 ID | `doudian.creative.fuwu.service.downshelf` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/service/downshelf` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4765 |
| 更新日期 | `2023-09-19` |

## 接口说明

- 文档书: 创意管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_biz_id` | body | string | 是 | 外部业务id(如模板Code) | `12345` |
| `reason` | body | string | 是 | 下架服务原因 | `因无法使用服务下架` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=fuwu.service.downshelf&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
