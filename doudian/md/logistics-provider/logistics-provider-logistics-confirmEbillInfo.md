# logistics.confirmEbillInfo

> 校验面单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.confirmEbillInfo` |
| 中文名 | 校验面单信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/confirmEbillInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6894 |
| 更新日期 | `2024-09-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 物流商平台用户id | `123aa` |
| `scene` | body | string | 否 | 1、小程序用户查件 2、小程序用户预约派送 3、小程序用户改地址 4、客服进线查件 5、可补充新增 | `1` |
| `company` | body | string | 否 | 快递公司 | `shunfeng` |
| `waybill_code` | body | string | 否 | 运单号 | `SF3103018291111` |
| `mobile` | body | string | 否 | 手机号后四位 | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/confirmEbillInfo?app_key=your_appkey_here&method=logistics.confirmEbillInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `is_conform` | boolean | 是否一致 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 订单信息不存在（sub_code: isv.business-failed:10014） | 检查运单号正确性 |
| `80000` | 风控拦截 / 风控拦截，查询频率较高或触发风险管控（sub_code: isv.risk-control-failed:15104） | 稍后重试或联系客服 |
| `40004` | 非法的参数 / 参数错误，必传参数为空或其他参数错误（sub_code: isv.parameter-invalid:4006） | 检查必传参数 |

## 响应示例

成功：

```json
{
  "data": {
    "is_conform": "true"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:10014",
  "sub_msg": "订单信息不存在"
}
```

## 备注
