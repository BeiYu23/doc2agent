# maintenance.order.supplierCompleteException

> 维修异常

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.phone-industry.maintenance.order.supplierCompleteException` |
| 中文名 | 维修异常 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1520/6643 |
| 更新日期 | `2024-06-20` |

## 接口说明

- 文档书: 手机行业管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `"test"` |
| `operate_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `"2024-02-12 12:12:56"` |
| `operation_no` | body | string | 是 | 实操单号 | `"BSO354354"` |
| `exception_code` | body | mixed | 是 | 异常code，1-需要返厂维修 | `1` |
| `expect_fix_time` | body | string | 否 | 预计解决时间，返厂维修时必传，格式："yyyy-MM-dd HH:mm:ss" | `"2024-02-12 12:12:56"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=maintenance.order.supplierCompleteException&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
