# 支持仓储服务商查询货品数据

> instantShopping.querySpuGoodsInfo — 支持仓储服务商查询货品数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 支持仓储服务商查询货品数据 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-instantShopping-querySpuGoodsInfo` |
| 接口 ID | `doudian.warehouse.instantShopping.querySpuGoodsInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/7128 |
| 更新日期 | `2024-12-04` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `goods_ids` | body | array | 是 | 抖音给到的货品ID | `["1","2"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.querySpuGoodsInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `spu_goods_info_list` | array | 货品结果List | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 入参不正确（sub_code: isv.parameter-invalid:40001） | 调整为正确入参 |

## 响应示例

成功：

```json
{
  "data": {
    "spu_goods_info_list": [
      {
        "category_detail": {
          "first_c_name": "鲜花速递/花卉仿真/绿植园艺",
          "first_cid": "20107",
          "fourth_c_name": "四级类目名",
          "fourth_cid": "0",
          "second_c_name": "鲜花速递",
          "second_cid": "21698",
          "third_c_name": "三级类目名",
          "third_cid": "0"
        },
        "goods_bar_code_list": "[\"20202020\",\"212121\"]",
        "goods_id": "100011981",
        "goods_name": "19颗草莓6朵卡布奇诺草莓熊花束",
        "gross_height": "1000",
        "gross_length": "1000",
        "gross_weight": "1000",
        "gross_width": "1000",
        "net_height": "1000",
        "net_length": "1000",
        "net_weight": "1000",
        "net_width": "1000",
        "org_shop_id": "1000110",
        "sku_spec_name": [
          {
            "name": "默认",
            "value": "默认"
          }
        ],
        "temperature_layer": "1"
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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "入参不正确"
}
```

## 备注
