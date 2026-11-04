# 提供给isv，根据店铺获取线索

> product.isv.getClueList — 提供给isv，根据店铺获取线索

| 元信息 | 值 |
| --- | --- |
| 中文名 | 提供给isv，根据店铺获取线索 |
| 文档地址 | `/docs/doudian/product/product-product-isv-getClueList` |
| 接口 ID | `doudian.product.product.isv.getClueList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/isv/getClueList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2195 |
| 更新日期 | `2024-02-28` |

## 接口说明

- 文档书: 商品API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `source_channel_code` | body | string | 是 | 渠道，competitive：搜索热招商机，shop_exclusive：店铺专属商机，query_none_less：搜索蓝海商机，industry_selected：行业趋势商机 | `competitive` |
| `first_cid` | body | mixed | 否 | 一级类目id | `20005` |
| `second_cid` | body | mixed | 否 | 二级类目id | `20224` |
| `clue_info` | body | string | 否 | 品牌名或线索名 | `线索名称` |
| `current` | body | mixed | 是 | 当前页(从1开始) | `1` |
| `page_size` | body | mixed | 是 | 每页条数 | `100` |
| `competitive_clue_type` | body | mixed | 否 | 爆款类型，0：趋势爆款，1：行业爆款，2：品牌爆款，3：货源地爆款 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/isv/getClueList?app_key=your_appkey_here&method=product.isv.getClueList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回值 | `` |
| `total` | mixed | 总条数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 查询店铺失败（sub_code: isp.service-error:501） | 联系开发者 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:502） | 联系开发者 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:503） | 联系开发者 |
| `40004` | 非法的参数 / 分页参数不合法（sub_code: isv.parameter-invalid:504） | 分页参数不合法 |
| `40004` | 非法的参数 / 渠道类型不存在（sub_code: isv.parameter-invalid:505） | 渠道类型不存在 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:500） | 联系开发者 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "brand_id": "100002",
        "brand_name_cn": "示例品牌名称",
        "brand_name_en": "Example Brand Name",
        "clue_id": "29979",
        "clue_name": "线索名称",
        "first_cid": "20005",
        "first_name": "女装",
        "pic_url": "http://p3-tt.byteimg.com/image-pair-YOUR_SECRET_KEY~tplv-sfvsc053ke-image.image",
        "second_cid": "20224",
        "second_name": "连衣裙"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:501",
  "sub_msg": "查询店铺失败"
}
```

## 备注
