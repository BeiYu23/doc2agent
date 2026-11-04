# contentAIGC.getAIVideoCreditOpen

> 查询商家可用积分与充值地址

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.doubao.contentAIGC.getAIVideoCreditOpen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/contentAIGC/getAIVideoCreditOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1627/8655 |
| 更新日期 | `2026-09-23` |

## 接口说明

- 文档书: 豆包工作（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/contentAIGC/getAIVideoCreditOpen?app_key=your_appkey_here&method=contentAIGC.getAIVideoCreditOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `available_credits` | mixed | 成功时必返，剩余可用积分；参考 creation.GetCreditInfoOpen 的 CreditBalance。 | `` |
| `recharge_url` | string | 真实充值页面地址，未配置或无法取得时缺省。 | `` |
| `base_resp` | object | 查询失败不能用余额 0 代替。 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:1000000） | 请稍后重试；创建任务重试时请保持原 requestId 不变。若持续失败，请联系技术支持。 |
| `40004` | 非法的参数 / 请求参数错误（sub_code: isv.parameter-invalid:1000001） | 请按接口文档检查必填字段、参数类型及取值后重试。 |

## 响应示例

成功：

```json
{
  "data": {
    "available_credits": "0",
    "base_resp": {
      "extra": {},
      "status_code": "0",
      "status_message": ""
    },
    "recharge_url": ""
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
  "sub_code": "isp.service-error:1000000",
  "sub_msg": "系统异常"
}
```

## 备注
