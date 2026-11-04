# logistics.majorAppliances.pushOrderInfo

> 服务商推进取件单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.majorAppliances.pushOrderInfo` |
| 中文名 | 服务商推进取件单状态 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8272 |
| 更新日期 | `2026-05-08` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pickup_order_id` | body | string | 否 | 取件单号 | `LBFxxx` |
| `push_type` | body | mixed | 否 | 推送类型 | `1: 推送取件员信息 2: 推送取件结果` |
| `courier_name` | body | string | 否 | 上门师傅姓名(回传上门师傅信息时必传) | `张三` |
| `courier_phone` | body | string | 否 | 上门师傅电话(回传上门师傅信息时必传) | `180xxxxxxxx` |
| `task_result` | body | string | 否 | 任务结果(已取件)(回告取件任务结果时必传) | `FETCHED` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.majorAppliances.pushOrderInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参错误，例如枚举值传错（sub_code: isv.parameter-invalid:12004） | 检查入参 |
| `40002` | 缺少必选参数 / 必选字段缺失（sub_code: isv.missing-parameter:12005） | 检查入参 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:10001） | 重试调用 |

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
  "sub_code": "isv.parameter-invalid:12004",
  "sub_msg": "入参错误，例如枚举值传错"
}
```

## 备注
