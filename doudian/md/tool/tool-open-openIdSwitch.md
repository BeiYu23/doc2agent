# open.openIdSwitch

> 提供抖音和抖店 Openid 转换功能

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.open.openIdSwitch` |
| 中文名 | 提供抖音和抖店 Openid 转换功能 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/open/openIdSwitch` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1973 |
| 更新日期 | `2022-06-02` |

## 接口说明

- 文档书: 工具API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `open_id` | body | string | 是 | 传入的openId | `fgdsgwerqwfdsfd` |
| `open_id_type` | body | string | 否 | openId类型，1-抖音openId 2-抖店openId | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/open/openIdSwitch?app_key=your_appkey_here&method=open.openIdSwitch&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `open_id` | string | 对应的openId | `dfsdfsgdrwds` |
| `open_id_type` | string | openId类型，1-抖音openId 2-抖店openId | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参不合法（sub_code: isv.parameter-invalid:100001） | 请检查入参 |
| `50002` | 业务处理失败 / 查询应用和小程序绑定关系失败（sub_code: isv.business-failed:300010） | 检查应用和小程序绑定关系 |
| `40004` | 非法的参数 / 入参不合法（sub_code: isv.parameter-invalid:100000） | 请检查入参 |

## 响应示例

成功：

```json
{
  "data": {
    "open_id": "dfsdfsgdrwds",
    "open_id_type": "2"
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
  "sub_code": "isv.parameter-invalid:100001",
  "sub_msg": "入参不合法"
}
```

## 备注
