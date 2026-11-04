# fuwu.writeOffUsageCount

> 核销已冻结的使用次数

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.fuwu.writeOffUsageCount` |
| 中文名 | 核销已冻结的使用次数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/writeOffUsageCount` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8349 |
| 更新日期 | `2026-06-23` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `outer_biz_id` | body | string | 否 | 外部业务ID(模板市场为模板code)，非必传，不可与serviceId同传 | `111` |
| `service_id` | body | mixed | 否 | 服务ID，非必传，不可与outerBizId同传 | `111` |
| `log_id` | body | string | 否 | 执行规定操作所调用openapi的log_id | `111` |
| `req_id` | body | string | 否 | 请求id, 作幂等键 | `111` |
| `write_off_cnt` | body | mixed | 否 | 核销次数 | `111` |
| `remark` | body | string | 否 | 备注，长度不超过1024 | `备注` |
| `is_unfreeze_all` | body | boolean | 否 | 是否解冻当前reqId冻结的全部次数，true时writeOffCnt必须为0 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/writeOffUsageCount?app_key=your_appkey_here&method=fuwu.writeOffUsageCount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
