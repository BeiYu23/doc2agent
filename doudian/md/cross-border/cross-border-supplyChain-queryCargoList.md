# supplyChain.queryCargoList

> 查询货品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.supplyChain.queryCargoList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/queryCargoList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6328 |
| 更新日期 | `2026-05-28` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | mixed | 是 | 当前页码 | `1` |
| `page_size` | body | mixed | 是 | 每页数量 | `10` |
| `cargo_code` | body | string | 否 | 货品编码 | `7344945371866677548` |
| `cargo_barcode` | body | string | 否 | 条形码 | `6924567890138` |
| `external_cargo_code` | body | string | 否 | 外部货品编码 | `22291` |
| `cargo_category_id` | body | mixed | 否 | 货品类目id | `22291` |
| `create_start_time` | body | mixed | 否 | 创建时间，开始 | `1704067200` |
| `create_end_time` | body | mixed | 否 | 创建时间，截止 | `1706659200` |
| `flatten_status` | body | mixed | 否 | 聚合状态.3-已生效,4 -已生效待审批,5-已生效审批拒绝, 6-草稿 | `3` |
| `bmp_code` | body | string | 否 | 行业身份编码 | `xiaodian.crossborder` |
| `cargo_barcode_list` | body | array | 否 | 批量查询条码 | `1111,22222` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/queryCargoList?app_key=your_appkey_here&method=supplyChain.queryCargoList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cargoList` | array | 返回值 | `` |
| `total` | mixed | 总数 | `1000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "cargoList": [
      {
        "barcode_list": "111111111",
        "cargo_code": "123456789",
        "cargo_name": "测试货品",
        "external_cargo_code": "1111",
        "first_cid": "1",
        "first_cname": "一级类目",
        "flatten_status": "3",
        "fourth_cid": "4",
        "fourth_cname": "四级类目名称",
        "is_need_valid": "1",
        "period_of_forbid_sale": "1",
        "period_of_forbid_take": "1",
        "period_of_validity": "1",
        "picture": "http://xxx.jgp",
        "second_cid": "2",
        "second_cname": "二级类目",
        "third_cid": "3",
        "third_cname": "三级类目名称"
      }
    ],
    "total": "1000"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
