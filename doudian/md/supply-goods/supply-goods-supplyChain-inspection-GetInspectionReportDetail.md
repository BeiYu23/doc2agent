# supplyChain.inspection.GetInspectionReportDetail

> 查询验机报告详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.inspection.GetInspectionReportDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/8264 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_report_id` | body | string | 否 | 报告id | `111111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.GetInspectionReportDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |
| `code` | mixed | 0 | `0` |
| `msg` | string | 运行信息 | `success` |

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
      "inspection_report": {
        "base_info": {
          "brand_id": "1121",
          "brand_name": "品牌名",
          "category_id": "1000007628",
          "category_name": "类目名",
          "collection_code": "标准集编码",
          "cover_image": {
            "appearance_image_type": "11",
            "url": "图片 URL"
          },
          "create_time": "11111",
          "fineness": "成色",
          "imei": "IMEI",
          "inspection_report_id": "验机报告 ID",
          "model_id": "1112",
          "model_name": "型号名",
          "qc_code": "质检中心的验机报告编号",
          "reject_reason": "驳回原因",
          "reject_time": "111111",
          "remark": "备注",
          "status": "111"
        },
        "flow_list": [
          {
            "flow_id": "质检流程的 ID",
            "flow_name": "质检流程的名称",
            "item_list": [
              {
                "item_code": "标准项code",
                "item_name": "标准项名称",
                "values": "标准项值"
              }
            ]
          }
        ],
        "image_info": {
          "appearance_images": [
            {
              "appearance_image_type": "外观图片类别",
              "url": "图片 URL"
            }
          ],
          "defect_images": [
            {
              "appearance_image_type": "1",
              "url": "图片 URL"
            }
          ]
        },
        "reject_detail_list": [
          {
            "appearance_image_type": "1",
            "reject_content_index": "0",
            "reject_content_type": "1",
            "reject_reason": "驳回原因"
          }
        ]
      }
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
