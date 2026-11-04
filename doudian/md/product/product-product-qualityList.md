# product.qualityList

> 查询店铺商品质量情况，对标后台商品成长中心

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.qualityList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/qualityList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/938 |
| 更新日期 | `2025-03-10` |

## 接口说明

- 文档书: 商品API（版本 V3.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 否 | 商品ID | `3502373827210525080` |
| `product_name` | body | string | 否 | 商品名字 | `奈克牌皮鞋` |
| `order_by` | body | string | 否 | 排序方式，降序“desc”，升序“asc”， 不传默认降序 | `desc` |
| `page` | body | number | 是 | 分页参数，页数从1开始 | `1` |
| `page_size` | body | number | 是 | 分页参数，每页大小，填写范围1~100； | `20` |
| `task_id` | body | number | 是 | 【已废弃】开发者可以传入：9999999999 | `11013491` |
| `diagnose_status` | body | array | 否 | 商品诊断状态，0-待诊断；1-待优化；2-已修改审核中；3-已优化；以前的status 字段因为配置错误已经删除，请使用此新字段 | `[1]` |
| `quality_score_version` | body | string | 否 | 质量分版本，枚举：new_quality_score-新版，middle_score-旧版中标质量分已废弃。 | `middle_score` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `quality_list` | array | 商品质量列表 | `` |
| `total` | number | 店铺待优化商品总量 | `50` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:2030003） | 补充必要参数 |
| `40004` | 非法的参数 / 参数值非法（sub_code: isv.parameter-invalid:2030004） | 按要求填写参数值 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:2030001） | 等待后重试 |
| `20000` | 系统错误 / 读取数据失败（sub_code: isp.service-error:2030201） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 2030013:读取商品失败（sub_code: isv.business-failed:2030013） | 系统异常，请稍后重试 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:2030003",
  "sub_msg": "缺少必要参数"
}
```

## 备注
