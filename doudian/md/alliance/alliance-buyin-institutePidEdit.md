# buyin.institutePidEdit

> 抖客PID 编辑

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.institutePidEdit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/institutePidEdit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1270 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pid` | body | string | 是 | PID | `dy_234_5767` |
| `site_name` | body | string | 是 | 推广位名称，不能和已有的重复(最长10个字符) | `微信2群` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/institutePidEdit?app_key=your_appkey_here&method=buyin.institutePidEdit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 推广位名称重复，请更换（sub_code: isv.parameter-invalid:1054） | 推广位名称重复，请更换 |
| `40004` | 非法的参数 / 无效 PID（sub_code: isv.parameter-invalid:1039） | 无效 PID |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 需【抖客】角色授权后访问（sub_code: isv.business-failed:4198） | 需【抖客】角色授权后访问 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1054",
  "sub_msg": "推广位名称重复，请更换"
}
```

## 备注
