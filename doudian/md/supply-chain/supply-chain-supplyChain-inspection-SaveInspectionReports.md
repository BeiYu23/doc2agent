# supplyChain.inspection.SaveInspectionReports

> 创建/编辑验机报告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.inspection.SaveInspectionReports` |
| 中文名 | 创建/编辑验机报告 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/8265 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_report_list` | body | array | 否 | 报告列表 | `` |
| `  └ image_info` | body | object | 否 | 验机报告图片信息 | `` |
| `    └ appearance_images` | body | array | 否 | 外观实拍图（TaggedImage） | `` |
| `      └ url` | body | string | 否 | 图片 URL | `http://ssxxxx` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类别 | `1` |
| `    └ defect_images` | body | array | 否 | 瑕疵实拍图 | `` |
| `      └ url` | body | string | 否 | 图片 URL | `图片 URL` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类别 | `1` |
| `  └ reject_detail_list` | body | array | 否 | 驳回详情列表 | `` |
| `    └ reject_content_type` | body | mixed | 否 | 驳回内容类型 | `0` |
| `    └ reject_content_index` | body | mixed | 否 | 驳回内容索引（从0开始） | `0` |
| `    └ appearance_image_type` | body | mixed | 否 | 实拍图类型（如果驳回内容是实拍图） | `实拍图类型（如果驳回内容是实拍图）` |
| `    └ reject_reason` | body | string | 否 | 驳回原因 | `驳回原因` |
| `  └ base_info` | body | object | 否 | 验机报告基础信息 | `` |
| `    └ inspection_report_id` | body | string | 否 | 验机报告 ID | `验机报告 ID` |
| `    └ reject_reason` | body | string | 否 | 驳回原因 | `驳回原因` |
| `    └ model_id` | body | string | 否 | 型号 ID | `型号 ID` |
| `    └ category_name` | body | string | 否 | 类目名 | `类目名` |
| `    └ qc_code` | body | string | 否 | 质检中心的验机报告编号 | `质检中心的验机报告编号` |
| `    └ brand_name` | body | string | 否 | 品牌名 | `品牌名` |
| `    └ remark` | body | string | 否 | 备注 | `备注` |
| `    └ collection_code` | body | string | 否 | 标准集编码 | `标准集编码` |
| `    └ brand_id` | body | string | 否 | 品牌 ID | `112` |
| `    └ create_time` | body | mixed | 否 | 创建时间（时间戳） | `1111111` |
| `    └ fineness` | body | string | 否 | 成色 | `成色` |
| `    └ reject_time` | body | mixed | 否 | 驳回时间（时间戳） | `1122211` |
| `    └ imei` | body | string | 否 | IMEI | `1112222` |
| `    └ status` | body | mixed | 否 | 状态 | `0` |
| `    └ model_name` | body | string | 否 | 型号名 | `型号名` |
| `    └ category_id` | body | string | 否 | 类目 ID | `1000007628` |
| `    └ cover_image` | body | object | 否 | 封面图（用于列表页展示） | `` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类别 | `外观图片类别` |
| `      └ url` | body | string | 否 | 图片 URL | `http://ssxxxx` |
| `  └ flow_list` | body | array | 否 | 质检流程列表 | `` |
| `    └ flow_id` | body | string | 否 | 质检流程的 ID | `质检流程的 ID` |
| `    └ flow_name` | body | string | 否 | 质检流程的名称 | `质检流程的名称` |
| `    └ item_list` | body | array | 否 | 质检项的列表 | `` |
| `      └ item_code` | body | string | 否 | 标准项code | `标准项code` |
| `      └ values` | body | array | 否 | 标准项值 | `标准项值` |
| `      └ item_name` | body | string | 否 | 标准项名称 | `标准项名称` |
| `merge_duplicate_imei` | body | boolean | 否 | 是否合并重复 IMEI 的报告 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.SaveInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 保存结果 | `` |
| `code` | mixed | 执行编码 | `0` |
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
      "result_list": [
        {
          "fail_reason": "保存失败原因",
          "inspection_report_id": "验机报告 ID",
          "is_duplicate_imei": "true",
          "succeed": "true"
        }
      ]
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
