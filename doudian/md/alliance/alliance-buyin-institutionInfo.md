# buyin.institutionInfo

> 获取机构信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.institutionInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/institutionInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2305 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/institutionInfo?app_key=your_appkey_here&method=buyin.institutionInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `institution_id` | number | 机构ID | `38989329849343243` |
| `colonel` | object | 团长信息 | `` |
| `mcn` | object | MCN信息 | `` |
| `douke` | object | 抖客信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 无效用户（sub_code: isv.business-failed:4157） | 无效用户 |

## 响应示例

成功：

```json
{
  "data": {
    "colonel": {
      "buyin_id": "78794839403200001",
      "name": "这是团长名称"
    },
    "douke": {
      "buyin_id": "78794839403200003",
      "name": "这是抖客名称"
    },
    "institution_id": "38989329849343243",
    "mcn": {
      "buyin_id": "78794839403200002",
      "name": "这是机构名称"
    }
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
