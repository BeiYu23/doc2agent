# inspection.getInspectionReportDetail

> 验机报告详情查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.getInspectionReportDetail` |
| 中文名 | 验机报告详情查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/getInspectionReportDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8253 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_report_id` | body | string | 是 | 验机报告id | `2021148867055063040` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/getInspectionReportDetail?app_key=your_appkey_here&method=inspection.getInspectionReportDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应msg | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数 (如：operator_info 身份信息为空、operator_id 为空，或 inspection_report_id 报告ID为空)（sub_code: isv.missing-parameter:-41003） | 请检查并传入必传参数 operator_info.operator_id 和 inspection_report_id |
| `50002` | 业务处理失败 / 业务处理失败 (如：获取质检报告详情失败)（sub_code: isv.business-failed:-41005） | 请检查 inspection_report_id 的有效性（如报告是否存在），或稍后重试 |
| `20000` | 系统错误 / 服务不可用 (如：获取质检报告详情失败，底层服务返回为空)（sub_code: isp.service-error:-41002） | 系统内部繁忙或异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "inspection_report": {
        "base_info": {
          "brand_id": "1621265926",
          "brand_name": "iPhone",
          "category_id": "1000007628",
          "category_name": "",
          "collection_code": "7457180029220159759_152",
          "cover_image": {
            "appearance_image_type": "10",
            "url": "xx"
          },
          "create_time": "1770714417",
          "fineness": "未拆封",
          "imei": "123451234512345",
          "inspection_report_id": "2021148867055063040",
          "model_id": "48446",
          "model_name": "iPhone 17 Pro Max",
          "qc_code": "QC11152105169211",
          "reject_reason": "",
          "reject_time": "-62135596800",
          "remark": "备注",
          "shop_id": "10581848",
          "status": "20"
        },
        "flow_list": [
          {
            "flow_id": "7611460237148815643",
            "flow_name": "基础信息",
            "item_list": [
              {
                "item_code": "7457181828446535988_2",
                "item_name": "购买渠道",
                "values": "国行"
              }
            ]
          }
        ],
        "image_info": {
          "appearance_images": [
            {
              "appearance_image_type": "10",
              "url": "xx"
            }
          ],
          "defect_images": [
            {
              "appearance_image_type": "11",
              "url": "xx"
            }
          ]
        },
        "reject_detail_list": [
          {
            "appearance_image_type": "0",
            "reject_content_index": "0",
            "reject_content_type": "0",
            "reject_reason": ""
          }
        ]
      }
    },
    "msg": ""
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:-41003",
  "sub_msg": "缺少必选参数 (如：operator_info 身份信息为空、operator_id 为空，或 inspection_report_id 报告ID为空)"
}
```

## 备注
