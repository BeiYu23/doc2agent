# buyin.kolLiveShare

> 获取达人直播间分享链接

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.kolLiveShare` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/kolLiveShare` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1724 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pid_info` | body | object | 是 | PID信息 | `` |
| `  └ pid` | body | string | 是 | 达人PID | `dy_10101245197859_1726220821_2656147525` |
| `  └ external_info` | body | string | 否 | 自定义字段，只允许 数字、字母和_，限制长度为40 | `123_456` |
| `need_qr_code` | body | boolean | 否 | 是否需要二维码(获取二维码将增加响应耗时，推荐false) | `false` |
| `platform` | body | mixed | 否 | 回流端标识 0：抖音 1：抖音极速版 | `0` |
| `need_zlink` | body | boolean | 否 | 是否需要zlink(默认返回，不需要可以填false) | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolLiveShare?app_key=your_appkey_here&method=buyin.kolLiveShare&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效的doudian_open_id（sub_code: isv.parameter-invalid:4149） | 无效的doudian_open_id |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 达人未开播（sub_code: isv.business-failed:4130） | 达人未开播 |
| `50002` | 业务处理失败 / 达人未开通分销业务（sub_code: isv.business-failed:4129） | 达人未开通分销业务 |
| `50002` | 业务处理失败 / 参数校验失败：无效 PID（sub_code: isv.business-failed:4102） | 无效 PID |
| `40004` | 非法的参数 / 回流平台参数非法（sub_code: isv.parameter-invalid:4122） | 回流平台参数非法 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_code": "isv.parameter-invalid:4149",
  "sub_msg": "无效的doudian_open_id"
}
```

## 备注
