# 仓库解绑门店

> open.appIpWhiteListDelete — 仓库解绑门店接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 仓库解绑门店 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-open-appIpWhiteListDelete` |
| 接口 ID | `doudian.warehouse.open.appIpWhiteListDelete` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/appIpWhiteListDelete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/1819 |
| 更新日期 | `2022-05-06` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ip_list` | body | array | 是 | ip地址列表 | `["1.2.3.4"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/appIpWhiteListDelete?app_key=your_appkey_here&method=open.appIpWhiteListDelete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
