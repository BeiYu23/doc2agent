# sms.getTobTrafficDrivingLinkList

> 查询引流链接

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.getTobTrafficDrivingLinkList` |
| 中文名 | 查询引流链接 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getTobTrafficDrivingLinkList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/8435 |
| 更新日期 | `2026-07-28` |

## 接口说明

- 文档书: 短信API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `link` | body | string | 否 | 链接 | `https://test-xxx.com/demo` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/getTobTrafficDrivingLinkList?app_key=your_appkey_here&method=sms.getTobTrafficDrivingLinkList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `list` | array | 结果 | `` |
| `total` | mixed | 总数 | `19` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "list": [
      {
        "jump_link": "https://test.com/path",
        "jump_link_domain": "test.com",
        "jump_link_domain_icp": "test-icp",
        "jump_link_domain_icp_body": "test-icpBody",
        "jump_link_path": "https://test-xxx.com/demo",
        "link": "https://test.com/path",
        "link_domain": "test.com",
        "link_domain_icp": "test-icp",
        "link_domain_icp_body": "test-icpBody",
        "link_path": "/path",
        "protocol": "https",
        "use_volc_link": "false"
      }
    ],
    "total": "19"
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
