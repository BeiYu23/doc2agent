# buyin.kolLivePreviewShare

> 达人直播预告转链

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.kolLivePreviewShare` |
| 中文名 | 达人直播预告转链 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/kolLivePreviewShare` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2006 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `live_appointment_id` | body | string | 是 | 直播预告Id | `123456789` |
| `pid` | body | string | 是 | pid | `dy_1234_4567_7890` |
| `platform` | body | mixed | 否 | 回流端标识 0：抖音 1：抖音极速版 | `0` |
| `external_info` | body | string | 否 | 自定义字段，只允许 数字、字母和_，限制长度为40 | `external_info_test` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/kolLivePreviewShare?app_key=your_appkey_here&method=buyin.kolLivePreviewShare&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 直播预告转链数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:4097） | 参数错误 |
| `40004` | 非法的参数 / 直播预约不存在或已删除/预告不属于该达人（sub_code: isv.parameter-invalid:4123） | 直播预约不存在或已删除/预告不属于该达人 |
| `50002` | 业务处理失败 / 达人已开播（sub_code: isv.business-failed:4124） | 达人已开播 |
| `20000` | 系统错误 / 直播预告转链异常（sub_code: isp.service-error:4125） | 直播预告转链异常 |
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
  "sub_code": "isv.parameter-invalid:4097",
  "sub_msg": "参数错误"
}
```

## 备注
