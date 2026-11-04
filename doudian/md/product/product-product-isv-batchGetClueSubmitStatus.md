# product.isv.batchGetClueSubmitStatus

> 批量查询线索的提报状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.isv.batchGetClueSubmitStatus` |
| 中文名 | 批量查询线索的提报状态 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isv/batchGetClueSubmitStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2318 |
| 更新日期 | `2022-08-23` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `productid_clueid_pair` | body | array | 是 | 线索ID和商品ID | `` |
| `  └ clue_id` | body | number | 是 | 线索ID | `无` |
| `  └ product_id` | body | number | 是 | 商品ID | `无` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/isv/batchGetClueSubmitStatus?app_key=your_appkey_here&method=product.isv.batchGetClueSubmitStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 批量查询的数据不得超过100（sub_code: isv.parameter-invalid:501） | 批量查询的数据不得超过100 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:502） | 联系管理员 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "audit_status": "无需填写",
        "clue_id": "无需填写",
        "product_id": "无需填写",
        "refused_reason": "无需填写",
        "submit_id": "无需填写"
      }
    ]
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
  "sub_code": "isv.parameter-invalid:501",
  "sub_msg": "批量查询的数据不得超过100"
}
```

## 备注
