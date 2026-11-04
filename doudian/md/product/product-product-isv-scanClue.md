# product.isv.scanClue

> 扫描获取商机中心全量线索信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.isv.scanClue` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isv/scanClue` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4801 |
| 更新日期 | `2023-10-20` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_id` | body | number | 是 | 线索Id（游标id） | `123` |
| `source_channel_code` | body | array | 是 | 渠道code，搜索热招：competitive，蓝海：query_none_less，行业趋势：industry_selected，低价：choice_low_price | `["query_none_less","industry_selected"]` |
| `page_size` | body | number | 是 | 限制200 | `100` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/isv/scanClue?app_key=your_appkey_here&method=product.isv.scanClue&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 线索列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:501） | 联系开发者 |
| `40004` | 非法的参数 / 渠道code限制错误（sub_code: isv.parameter-invalid:502） | 联系开发者 |
| `40004` | 非法的参数 / 分页参数错误（sub_code: isv.parameter-invalid:503） | pageSize不能小于等于0，不能超过限制值200 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "brand_id": "0",
        "brand_name_cn": "\"\"",
        "brand_name_en": "\"\"",
        "clue_id": "123",
        "clue_name": "我是线索",
        "demand_and_supply_rate": "4.56",
        "first_cid": "20029",
        "first_name": "彩妆/香水/美妆工具",
        "fourth_cid": "0",
        "fourth_name": "\"\"",
        "pic_url": "\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/SVCpeIZ_m_eb5bf8ba296491e6ed50bf4d5f4cb291_sx_38409_www\"",
        "price_max": "3990",
        "price_min": "1890",
        "query_name_cut_list": "[\"加绒\",\"加厚\"]",
        "search_heat": "577",
        "second_cid": "20570",
        "second_name": "男士彩妆",
        "third_cid": "0",
        "third_name": "\"\""
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:501",
  "sub_msg": "系统异常"
}
```

## 备注
