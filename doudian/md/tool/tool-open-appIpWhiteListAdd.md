# open.appIpWhiteListAdd

> 新增应用ip白名单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.appIpWhiteListAdd` |
| 中文名 | 新增应用ip白名单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/appIpWhiteListAdd` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1818 |
| 更新日期 | `2022-05-06` |

## 接口说明

- 文档书: 工具API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ip_list` | body | array | 否 | ip列表 | `` |
| `  └ ip` | body | string | 是 | ip（不能配置保留ip地址） | `1.2.3.4` |
| `  └ desc` | body | string | 是 | 描述 | `ip地址1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/appIpWhiteListAdd?app_key=your_appkey_here&method=open.appIpWhiteListAdd&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 100003:非法的ip:aliiwms.vinda.com（sub_code: isv.business-failed:100003） | 请检查ip信息 |
| `50002` | 业务处理失败 / 100006:你的操作过于频繁，请稍后重试（sub_code: isv.business-failed:100006） | 100006:你的操作过于频繁，请稍后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:100003",
  "sub_msg": "100003:非法的ip:aliiwms.vinda.com"
}
```

## 备注
