# supplyChain.inspection.ListInspectionReports

> 查询质检报告列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.inspection.ListInspectionReports` |
| 中文名 | 查询质检报告列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/8275 |
| 更新日期 | `2026-05-11` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_report_id_list` | body | array | 否 | 验机报告 ID 列表 | `["111"]` |
| `status` | body | mixed | 否 | 状态查询 | `1` |
| `imei_list` | body | array | 否 | IMEI | `["111"]` |
| `product_id_list` | body | array | 否 | 商品 ID 列表 | `["111"]` |
| `product_name` | body | string | 否 | 商品名称 | `商品名称` |
| `remark` | body | string | 否 | 备注 | `备注` |
| `brand_id_list` | body | array | 否 | 品牌 ID 列表 | `["111"]` |
| `create_time_end` | body | mixed | 否 | 创建时间范围 - 截止（包含） | `1111` |
| `model_id_list` | body | array | 否 | 型号 ID 列表 | `["111"]` |
| `create_time_begin` | body | mixed | 否 | 创建时间范围 - 起始（包含） | `11111` |
| `page` | body | mixed | 否 | 页码 | `11` |
| `page_size` | body | mixed | 否 | 每页大小 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.ListInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |
| `code` | mixed | 执行结果 | `0` |
| `msg` | string | 执行信息 | `success` |

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
      "inspection_report_list": [
        {
          "allowed_operation_type": [
            {}
          ],
          "base_info": {
            "brand_id": "品牌 ID",
            "brand_name": "品牌名",
            "category_id": "类目 ID",
            "category_name": "类目名",
            "collection_code": "标准集编码",
            "cover_image": {
              "appearance_image_type": "1",
              "url": "图片 URL"
            },
            "create_time": "11111",
            "fineness": "成色",
            "imei": "IMEI",
            "inspection_report_id": "验机报告 ID",
            "model_id": "型号 ID",
            "model_name": "型号名",
            "qc_code": "111111",
            "reject_reason": "驳回原因",
            "reject_time": "11111",
            "remark": "备注",
            "status": "1"
          },
          "bound_product_list": [
            {
              "check_status": "0",
              "image_url": "商品图片 URL",
              "product_id": "商品 ID",
              "product_name": "商品名称",
              "sku_list": [
                {
                  "sku_id": "SKU ID",
                  "sku_name": "SKU 名称",
                  "spec_id": "规格 ID"
                }
              ],
              "status": "0"
            }
          ]
        }
      ],
      "status_count_map": {},
      "total": "1"
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
