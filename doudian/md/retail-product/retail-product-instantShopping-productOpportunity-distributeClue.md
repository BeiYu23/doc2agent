# instantShopping.productOpportunity.distributeClue

> 商机发品流程：获取商机线索->发品传入商机参数
1、此接口为商机线索的分发接口，可获取线索id和线索名称；
2、发品时（/product/addV2 & YOUR_SECRET_KEY）要填充商机线索参数recruit_inf

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-product.instantShopping.productOpportunity.distributeClue` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1570/7476 |
| 更新日期 | `2025-05-22` |

## 接口说明

- 文档书: 商品管理API【即时零售】（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | string | 是 | 页码，从1开始 | `1` |
| `cate1` | body | array | 否 | 一级类目id | `111` |
| `cate2` | body | array | 否 | 二级类目id | `222` |
| `query` | body | string | 否 | 搜索词 | `榴莲` |
| `source` | body | number | 是 | 默认10014 | `10014` |
| `size` | body | string | 是 | 单页数量，最大20 | `20` |
| `cate3` | body | array | 否 | 三级类目id | `333` |
| `cate4` | body | array | 否 | 四级类目id | `444` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/ShopActivityList?app_key=your_appkey_here&method=buyin.ShopActivityList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:401） | 参数错误，请检查请求参数 |
| `20000` | 系统错误 / 系统错误，获取商机失败（sub_code: isp.service-error:500） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "activity_desc": "一个活动",
        "activity_id": "54321",
        "activity_kind": "1",
        "activity_name": "一个活动",
        "apply_end_time": "2022-02-10",
        "apply_num": "11",
        "apply_start_time": "2022-01-10",
        "apply_status": "0",
        "audit_pass_num": "11",
        "colonel_buyin_id": "647819735141426187",
        "commission_rate": "10.5",
        "estimated_single_sale": "100",
        "history_order_num": "10",
        "history_single_product_num": "10",
        "institution_id": "647819735141426187",
        "institution_name": "一个团长",
        "phone_num": "15671111111",
        "service_rate": "10.5",
        "wechat_id": "1233"
      }
    ],
    "next_cursor": "oiofw00902j43njl..232/232",
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
  "sub_code": "isv.parameter-invalid:401",
  "sub_msg": "参数错误"
}
```

## 备注
