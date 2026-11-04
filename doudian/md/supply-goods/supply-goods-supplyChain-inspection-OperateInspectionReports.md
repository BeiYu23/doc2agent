# supplyChain.inspection.OperateInspectionReports

> 操作验机报告（绑定/解绑 SKU、上架/下架）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.inspection.OperateInspectionReports` |
| 中文名 | 操作验机报告（绑定/解绑 SKU、上架/下架 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/8263 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operate_type` | body | mixed | 否 | 操作类型 1.绑定 2.解绑 3.上架 4.下架 5.更新备注信息 | `2` |
| `operation_target_list` | body | array | 否 | 待操作的报告列表 | `` |
| `  └ sku_for_bind_list` | body | array | 否 | 绑定列表 | `` |
| `    └ product_sku_id` | body | string | 否 | 分销品sku | `1111122` |
| `    └ product_id` | body | string | 否 | 分销品id | `1112221` |
| `  └ remark` | body | string | 否 | 备注信息 | `备注信息` |
| `  └ inspection_report_id` | body | string | 否 | 报告id | `11122111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.OperateInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |
| `code` | mixed | 执行编码 | `0` |
| `msg` | string | 执行结果 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "inspection_report_operate_result_map": {}
    },
    "msg": "success"
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
