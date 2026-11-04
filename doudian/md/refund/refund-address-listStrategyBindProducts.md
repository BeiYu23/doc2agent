# address.listStrategyBindProducts

> 分页获取地址库策略绑定的商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.address.listStrategyBindProducts` |
| 中文名 | 分页获取地址库策略绑定的商品 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/listStrategyBindProducts` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6922 |
| 更新日期 | `2024-10-08` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `strategy_id` | body | string | 否 | 策略id，必传，多地址策略对应的ID. | `AFS7418493389946110223` |
| `page` | body | mixed | 否 | 页码,从1开始， | `1` |
| `page_size` | body | mixed | 否 | 每页数目,最大100。地址策略目前最多支持拉取1w条记录，翻页数量超过1w会被系统拦截。 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/listStrategyBindProducts?app_key=your_appkey_here&method=address.listStrategyBindProducts&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 绑定商品总数 | `100` |
| `page` | mixed | 当前页码; | `1` |
| `page_size` | mixed | 每页数量; | `20` |
| `product_list` | array | 绑定商品列表; | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误，请稍后重试（sub_code: isv.parameter-invalid:4000） | 根据返回的错误信息，自行调整请求参数入参后重试。如果多次重试后无法解决问题，可以在开放平台提工单请求抖店同学协助。 |
| `40004` | 非法的参数 / 当前最多支持拉取10000条数据（sub_code: isv.parameter-invalid:100012） | 调整求参数中的page或者page_size，将二者乘积总量降低到10000以内。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 重试，如果多次重试后无法解决问题，可以在开放平台提工单寻求抖店工作人员帮助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 重试，如果多次重试后无法解决问题，可以在开放平台提工单寻求抖店工作人员帮助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3001） | 重试，如果多次重试后无法解决问题，可以在开放平台提工单寻求抖店工作人员帮助。 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "1",
    "page_size": "20",
    "product_list": [
      {
        "image": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/bMLccs_m_3313dab415e12933e72fd231f4b71515_sx_1750121_www1200-1200",
        "product_id": "3709228738131656945",
        "product_name": "时尚短袖T恤黑白两色背面艺术图案上衣夏季半袖小众宽松印花"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.parameter-invalid:4000",
  "sub_msg": "参数错误，请稍后重试"
}
```

## 备注
