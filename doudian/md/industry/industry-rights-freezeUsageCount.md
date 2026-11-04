# rights.freezeUsageCount

> 冻结权益使用次数

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.rights.freezeUsageCount` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/rights/freezeUsageCount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8348 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `freeze_cnt` | body | mixed | 否 | 冻结次数 | `10` |
| `outer_biz_id` | body | string | 否 | 外部业务ID(模板市场为模板code)，非必传，不可与serviceId同传 | `6859718390706503687` |
| `service_id` | body | mixed | 否 | 服务ID，非必传，不可与outerBizId同传 | `1111` |
| `log_id` | body | string | 否 | 执行规定操作所调用openapi的log_id | `111` |
| `req_id` | body | string | 否 | 请求id, 作幂等键 | `isv_service1#user1#202312251010999` |
| `remark` | body | string | 否 | 备注，长度不超过1024 | `备注` |
| `auto_deduct_usage` | body | boolean | 否 | 是否自动扣减冻结次数，true：7天之后未核销自动流转至扣减 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/rights/freezeUsageCount?app_key=your_appkey_here&method=rights.freezeUsageCount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

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
