# open.appIpWhiteListGet

> 应用ip白名单查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.appIpWhiteListGet` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/appIpWhiteListGet` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1891 |
| 更新日期 | `2022-05-07` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ip_like` | body | string | 否 | ip模糊匹配 | `1.2.3.4` |
| `page_index` | body | number | 否 | 第几页,从0开始 | `0` |
| `page_size` | body | number | 否 | 每页的个数 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/appIpWhiteListGet?app_key=your_appkey_here&method=open.appIpWhiteListGet&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `app_ip_list` | array | ip列表 | `` |
| `total` | number | ip列表总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "app_ip_list": [
      {
        "desc": "服务器地址1",
        "ip": "1.2.3.4",
        "ip_from": "中国-浙江-杭州"
      }
    ],
    "total": "10"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
