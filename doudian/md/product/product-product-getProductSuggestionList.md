# product.getProductSuggestionList

> 查询诊断商品列表及其处理建议

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.getProductSuggestionList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getProductSuggestionList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/8339 |
| 更新日期 | `2026-08-06` |

## 接口说明

- 文档书: 商品API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | string | 是 | 页码，从1开始 | `1` |
| `page_size` | body | string | 是 | 每页数量。一页最多不超过100。 | `20` |
| `suggestion` | body | string | 否 | 与suggestion_list两个参数必传一个。商品处理建议：force_offline强制下架, suggest_offline建议下架, optimize牵引优化 | `force_offline` |
| `suggestion_list` | body | array | 否 | 与suggestion两个参数必传一个。支持批量查询商品处理建议 | `[optimize,force_offline]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/virtualServicePushCallRecord?app_key=your_appkey_here&method=power.virtualServicePushCallRecord&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_list` | array | 商品列表 | `` |
| `total` | number | 商品总条数 | `300` |
| `total_exposure_lower_cnt` | number | 预计释放曝光收益-最小值 | `0` |
| `total_exposure_upper_cnt` | number | 预计释放曝光收益-最大值 | `1000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 605023002:调用商品服务异常（sub_code: isv.business-failed:605023002） | 请稍后重试，若持续报错请提工单咨询。 |
| `50002` | 业务处理失败 / 10010:参数异常，suggestion和suggestion_list两个参数必传一个（sub_code: isv.business-failed:10010） | suggestion和suggestion_list两个参数必传一个 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "false"
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
  "sub_code": "isv.business-failed:605023002",
  "sub_msg": "605023002:调用商品服务异常"
}
```

## 备注
