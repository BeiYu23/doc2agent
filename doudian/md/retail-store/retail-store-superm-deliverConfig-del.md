# superm.deliverConfig.del

> 时效管理删除

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.deliverConfig.del` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/deliverConfig/del` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/3598 |
| 更新日期 | `2023-10-08` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `config_ids` | body | array | 是 | 配置id列表 | `45` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/deliverConfig/del?app_key=your_appkey_here&method=superm.deliverConfig.del&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40100） | 参数错误 |
| `50002` | 业务处理失败 / 数据转换错误（sub_code: isv.business-failed:50202） | 数据转换错误 |

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
  "sub_code": "isv.parameter-invalid:40100",
  "sub_msg": "参数错误"
}
```

## 备注
