# compass.getProductSaleData

> 电商罗盘商品销售数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.compass.compass.getProductSaleData` |
| 中文名 | 电商罗盘商品销售数据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/compass/getProductSaleData` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1020/2355 |
| 更新日期 | `2022-08-11` |

## 接口说明

- 文档书: 罗盘API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `date_type` | body | string | 是 | 时间类型，枚举值，近7天（21），近30天（23），近一天/自然日（2），自然周（3），自然月（4） | `21` |
| `product_ids` | body | array | 是 | 商品id列表 | `3521094105834869219` |
| `end_date` | body | string | 是 | 时间周期的结束时间，格式为 yyyyMMdd | `20220802` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/compass/getProductSaleData?app_key=your_appkey_here&method=compass.getProductSaleData&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 商品销售数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 621000704:调用下游失败，请稍后重试（sub_code: isv.business-failed:621000704） | 621000704:调用下游失败，请稍后重试 |
| `50002` | 业务处理失败 / 621000625:当前没有权限访问（sub_code: isv.business-failed:621000625） | 621000625:当前没有权限访问 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "click_ucnt": "1",
        "pay_amt": "1",
        "pay_combo_cnt": "1",
        "pay_ucnt": "1",
        "product_click_pay_ucnt_ratio": "0.3",
        "product_id": "3521094105834869219",
        "product_show_click_ucnt_ratio": "0.2",
        "show_cnt": "1",
        "show_ucnt": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:621000704",
  "sub_msg": "621000704:调用下游失败，请稍后重试"
}
```

## 备注
