# buyin.institutePidCreate

> 抖客PID创建

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.institutePidCreate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/institutePidCreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1273 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `media_type` | body | string | 是 | 推广媒体类型，0:其他, 1:微信, 2:QQ, 3:微博, 4:抖音, 5:头条 | `1` |
| `media_name` | body | string | 否 | 渠道名称，没有media_id时自动创建渠道；存在media_id时无效 | `微信1群` |
| `media_id` | body | number | 否 | 渠道ID，和media_name二选一 | `222` |
| `site_name` | body | string | 是 | 推广位名称(最长10个字符) | `张三` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/institutePidCreate?app_key=your_appkey_here&method=buyin.institutePidCreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pid` | string | 机构PID | `dy_xxx_xxx_xxx` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效渠道类型（sub_code: isv.parameter-invalid:1051） | 请检查渠道类型 |
| `40004` | 非法的参数 / 无效渠道名称（sub_code: isv.parameter-invalid:1050） | 请检查渠道名称 |
| `40004` | 非法的参数 / 无效推广位名称（sub_code: isv.parameter-invalid:1049） | 请检查推广位名称 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 请稍后重试 |
| `50002` | 业务处理失败 / 推广位名称重复，请更换（sub_code: isv.business-failed:1054） | 请检查推广位名称 |
| `50002` | 业务处理失败 / 没有此渠道（sub_code: isv.business-failed:1048） | 请检查渠道信息 |
| `50002` | 业务处理失败 / 最多可创建2000个推广位（sub_code: isv.business-failed:1052） | 最多可创建2000个推广位 |
| `50002` | 业务处理失败 / 需【抖客】角色授权后访问（sub_code: isv.business-failed:4198） | 需【抖客】角色授权后访问 |

## 响应示例

成功：

```json
{
  "data": {
    "pid": "dy_xxx_xxx_xxx"
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
  "sub_code": "isv.parameter-invalid:1051",
  "sub_msg": "无效渠道类型"
}
```

## 备注
