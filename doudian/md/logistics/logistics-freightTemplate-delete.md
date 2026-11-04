# freightTemplate.delete

> 删除运费模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.freightTemplate.delete` |
| 中文名 | 删除运费模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/freightTemplate/delete` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/6200 |
| 更新日期 | `2026-09-23` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_id` | body | mixed | 是 | 运费模板id | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/freightTemplate/delete?app_key=your_appkey_here&method=freightTemplate.delete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_id` | mixed | 运费模板id | `12345` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:211000006） | 重试 |
| `50002` | 业务处理失败 / 运费模板被锁定（sub_code: isv.business-failed:211000034） | 解锁运费模板后重试 |
| `40004` | 非法的参数 / 小时达店铺不能删除模板（sub_code: isv.parameter-invalid:211000231） | 无 |
| `20000` | 系统错误（sub_code: isp.service-error:211000208） | 重试 |
| `20000` | 系统错误（sub_code: isp.service-error:10001） | 重试 |
| `50002` | 业务处理失败 / 运费模板已关联商品（sub_code: isv.business-failed:10011） | 该运费模板已关联"渠道品"、"售卖中"、"审核中"、"审核通过待上架"状态的商品，请解除关联后再删除 |
| `50002` | 业务处理失败 / 该运费模板已关联门店（sub_code: isv.business-failed:10012） | 该运费模板已关联门店，请解除关联后再删除 |

## 响应示例

成功：

```json
{
  "data": {
    "template_id": "12345"
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
  "sub_code": "isp.service-error:211000006",
  "sub_msg": "系统错误"
}
```

## 备注
