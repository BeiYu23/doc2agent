# inspection.saveInspectionReports

> 创建/编辑验机报告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.saveInspectionReports` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/saveInspectionReports` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8259 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_report_list` | body | array | 否 | 需要创建/保存的验机报告列表 | `` |
| `  └ reject_detail_list` | body | array | 否 | 驳回详情列表 | `` |
| `    └ appearance_image_type` | body | mixed | 否 | 实拍图类型（如果驳回内容是实拍图） enum InspectionReportAppearanceImageType {     Unknown               = 0  // 其他     ScreenBack            = 10 // 屏幕背面     ScreenFront           = 11 // 屏幕正面     FrameTop              = 20 // 顶部边框     FrameBottom           = 21 // 底部边框     FrameLeft             = 22 // 左边框     FrameRight            = 23 // 右边框     FrameTopLeft45        = 24 // 顶-左边框 45°     FrameTopRight45       = 25 // 顶-右边框 45°     FrameBottomLeft45     = 26 // 底-左边框 45°     FrameBottomRight45    = 27 // 底-右边框 45° } | `0` |
| `    └ reject_reason` | body | string | 否 | 驳回原因 | `` |
| `    └ reject_content_type` | body | mixed | 否 | 驳回内容类型 enum InspectionReportRejectContentType {     AppearanceImage = 1 // 实拍图     DefectImage     = 2 // 瑕疵图 } | `1` |
| `    └ reject_content_index` | body | mixed | 否 | 驳回内容索引（从0开始） | `0` |
| `  └ base_info` | body | object | 否 | 验机报告基础信息 | `` |
| `    └ reject_reason` | body | string | 否 | 驳回原因 | `` |
| `    └ status` | body | mixed | 否 | 状态 | `` |
| `    └ model_id` | body | string | 否 | 型号 ID | `559043` |
| `    └ category_name` | body | string | 否 | 类目名 | `` |
| `    └ brand_id` | body | string | 否 | 品牌 ID | `685293256` |
| `    └ qc_code` | body | string | 否 | 质检中心的验机报告编号 | `` |
| `    └ create_time` | body | mixed | 否 | 创建时间（时间戳） | `` |
| `    └ fineness` | body | string | 否 | 成色 | `` |
| `    └ inspection_report_id` | body | string | 否 | 验机报告 ID（填写了此id代表编辑报告，未填代表创建新报告） | `2026906645216366592` |
| `    └ model_name` | body | string | 否 | 型号名 | `iPhone 17 Pro Max` |
| `    └ imei` | body | string | 否 | IMEI | `123451234512345` |
| `    └ remark` | body | string | 否 | 备注 | `验机报告备注` |
| `    └ category_id` | body | string | 否 | 类目 ID | `1000007628` |
| `    └ std_category_name` | body | string | 否 | 标准类目名 | `` |
| `    └ brand_name` | body | string | 否 | 品牌名 | `APPLE/苹果` |
| `    └ reject_time` | body | mixed | 否 | 驳回时间（时间戳） | `` |
| `    └ std_category_id` | body | string | 否 | 标准类目 ID | `` |
| `    └ cover_image` | body | object | 否 | 封面图（用于列表页展示） | `` |
| `      └ url` | body | string | 否 | 图片 URL | `xx` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类别 enum InspectionReportAppearanceImageType {     Unknown               = 0  // 其他     ScreenBack            = 10 // 屏幕背面     ScreenFront           = 11 // 屏幕正面     FrameTop              = 20 // 顶部边框     FrameBottom           = 21 // 底部边框     FrameLeft             = 22 // 左边框     FrameRight            = 23 // 右边框     FrameTopLeft45        = 24 // 顶-左边框 45°     FrameTopRight45       = 25 // 顶-右边框 45°     FrameBottomLeft45     = 26 // 底-左边框 45°     FrameBottomRight45    = 27 // 底-右边框 45° } | `10` |
| `    └ collection_code` | body | string | 否 | 标准集编码（需要优先查询/inspection/getStandardCollection接口拿到标准集信息） | `7457180029220159759_152` |
| `  └ image_info` | body | object | 否 | 验机报告图片信息 | `` |
| `    └ defect_images` | body | array | 否 | 瑕疵实拍图 | `` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类别 enum InspectionReportAppearanceImageType {     Unknown               = 0  // 其他     ScreenBack            = 10 // 屏幕背面     ScreenFront           = 11 // 屏幕正面     FrameTop              = 20 // 顶部边框     FrameBottom           = 21 // 底部边框     FrameLeft             = 22 // 左边框     FrameRight            = 23 // 右边框     FrameTopLeft45        = 24 // 顶-左边框 45°     FrameTopRight45       = 25 // 顶-右边框 45°     FrameBottomLeft45     = 26 // 底-左边框 45°     FrameBottomRight45    = 27 // 底-右边框 45° } | `10` |
| `      └ url` | body | string | 否 | 图片 URL | `xx` |
| `    └ appearance_images` | body | array | 否 | 外观实拍图（TaggedImage） | `` |
| `      └ appearance_image_type` | body | mixed | 否 | 外观图片类型 enum InspectionReportAppearanceImageType {     Unknown               = 0  // 其他     ScreenBack            = 10 // 屏幕背面     ScreenFront           = 11 // 屏幕正面     FrameTop              = 20 // 顶部边框     FrameBottom           = 21 // 底部边框     FrameLeft             = 22 // 左边框     FrameRight            = 23 // 右边框     FrameTopLeft45        = 24 // 顶-左边框 45°     FrameTopRight45       = 25 // 顶-右边框 45°     FrameBottomLeft45     = 26 // 底-左边框 45°     FrameBottomRight45    = 27 // 底-右边框 45° } | `10` |
| `      └ url` | body | string | 否 | 图片 URL | `xx` |
| `  └ flow_list` | body | array | 否 | 质检流程列表 | `` |
| `    └ item_list` | body | array | 否 | 质检项的列表 | `` |
| `      └ item_code` | body | string | 否 | 标准项code | `7457181828446535988_2` |
| `      └ item_name` | body | string | 否 | 标准项名称 | `` |
| `      └ values` | body | array | 否 | 标准项值 | `国行` |
| `    └ flow_name` | body | string | 否 | 质检流程的名称 | `` |
| `    └ flow_id` | body | string | 否 | 质检流程的 ID | `7611460237148815643` |
| `merge_duplicate_imei` | body | boolean | 否 | 是否合并重复 IMEI 的报告（创建新报告时，控制IMEI重复时是编辑原有报告内容还是报错拦截） | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/saveInspectionReports?app_key=your_appkey_here&method=inspection.saveInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数（如 operator_info , operator_info.operator_id , inspection_report_list , base_info 不能为空）（sub_code: isv.missing-parameter:-41003） | 请检查并补充请求体中缺失的必传字段 |
| `40004` | 非法的参数 / 传入的参数非法或不在允许范围内（例如 operator_id 非法、类目ID/型号ID不在可配置列表中、质检标准集不匹配或必填项未满足）（sub_code: isv.parameter-invalid:-41004） | 请根据错误提示检查类目ID、型号ID及标准集流等参数的正确性 |
| `50002` | 业务处理失败 / 保存质检报告失败（sub_code: isv.business-failed:-41005） | 请检查报告数据是否正确，若重试仍失败请联系服务提供方 |
| `20000` | 系统错误 / 保存质检报告失败，服务无响应（sub_code: isp.service-error:-41002） | 服务端内部异常，请稍后重试或联系服务提供方 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "result_list": [
        {
          "fail_reason": "",
          "inspection_report_id": "2026906645216366592",
          "is_duplicate_imei": "false",
          "succeed": "true"
        }
      ]
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
  "sub_msg": "缺少必选参数（如 operator_info , operator_info.operator_id , inspection_report_list , base_info 不能为空）"
}
```

## 备注
