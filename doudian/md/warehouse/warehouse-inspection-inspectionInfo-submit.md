# inspection.inspectionInfo.submit

> 品控中心-质检结果回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.inspection.inspectionInfo.submit` |
| 中文名 | 品控中心-质检结果回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/inspectionInfo/submit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6768 |
| 更新日期 | `2025-10-24` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inspection_result_list` | body | array | 否 | 质检结果 | `` |
| `  └ is_re_inspection` | body | boolean | 否 | 是否复检 | `false` |
| `  └ inspection_items` | body | array | 否 | 标准项 | `` |
| `    └ material_info_list` | body | array | 否 | 填写材料信息，根据获取检测模版接口下发的模版，上传符合条件的材料数据 | `` |
| `      └ select_item_list` | body | array | 否 | 材料类型为【单选】、【多选】时需要填充的信息 | `` |
| `        └ select_code` | body | string | 否 | 填写模版下发的select_code值 | `item_code_1_test` |
| `      └ files` | body | array | 否 | 材料类型为【图片】、【视频】时需要填充的信息 | `` |
| `        └ url` | body | string | 否 | 图片、视频的url，需要保证能正常下载 | `http://xx.jpg` |
| `      └ material_rule_id` | body | number | 否 | 材料id | `75623718441` |
| `      └ text` | body | string | 否 | 材料类型为【数字】、【单行文本】、【多行文本】时需要填充的信息 | `测试` |
| `    └ material_info` | body | object | 否 | 填写材料信息，只给二手3C业务场景定制使用，其余场景使用material_info_list字段填写材料信息 | `` |
| `      └ text` | body | string | 否 | 文本形式结果 | `九成新` |
| `    └ item_code` | body | string | 否 | 标准项code | `7369142527871615258_6` |
| `  └ reject_reason_code` | body | string | 否 | 驳回原因code 【Q301】禁售型号: 老旧型号  【Q302】成色不符: 成色差异驳回 【Q303】货不对版或商品信息不一致 | `Q301` |
| `  └ img_url` | body | array | 否 | 质检结果图片url,最多上传30张，图片大小不超过2MB。 | `http://xxxx` |
| `  └ inspection_result` | body | number | 否 | 质检结果枚举，1-合格，2-不合格 | `1` |
| `  └ remark` | body | string | 否 | 备注 | `具体备注信息` |
| `biz_code` | body | string | 是 | 业务身份参数，固定：second_hand_inspection | `second_hand_inspection` |
| `task_type` | body | string | 是 | 业务身份参数，固定：each_goods_inspection | `each_goods_inspection` |
| `order_code` | body | string | 是 | 订单码 | `1057157943` |
| `event_time` | body | number | 否 | 结果回传时间秒级时间戳，如果传入则以传入为准，不传则以接口调用时间作为回传时间 | `1719370910` |
| `collection_code` | body | string | 是 | 示例如下(具体的标准集code需要对接研发核实，后续业务标准集如果有变动，也需要修改标准集code参数) 1.平板传入：7369403576672141577_21 2.笔记本电脑传入：7369424017386406171_23 3.手机传入：7369157534777409802_22 | `7369403576672141577_21` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 通用参数错误（sub_code: isv.parameter-invalid:30000） | 确认入参 |
| `40004` | 非法的参数 / 上传结果个数不正确，共xx条任务（sub_code: isv.parameter-invalid:30201） | 上传正确个数的结果 |
| `40004` | 非法的参数 / 备注超出限制（sub_code: isv.parameter-invalid:30202） | 备注需要在1000字内 |
| `40004` | 非法的参数 / 驳回原因未填写（sub_code: isv.parameter-invalid:30203） | 不合格需要填写驳回原因 |
| `40004` | 非法的参数 / 图片大小超出限制（sub_code: isv.parameter-invalid:30204） | 图片大小最大不超过10MB |
| `40004` | 非法的参数 / 图片个数超出限制（sub_code: isv.parameter-invalid:30205） | 单个质检结果最多50张报告 |
| `20000` | 系统错误（sub_code: isp.service-error:50000） | 联系研发 |
| `50002` | 业务处理失败 / 50003:tosClient.PutObject error: success=-1 httpCode=429 code=8002 message=too many concurrency update cas conflict, please try again later. remoteAddr=[fdbd:dc02:22:517::35]:8789 reqID=527e4d3c7a66521d673c7a66-a9e9123, objectId: 17320167424662872960c69bc（sub_code: isv.business-failed:50003） | 50003:tosClient.PutObject error: success=-1 httpCode=429 code=8002 message=too many concurrency update cas conflict, please try again later. remoteAddr=[fdbd:dc02:22:517::35]:8789 reqID=527e4d3c7a66521d673c7a66-a9e9123, objectId: 17320167424662872960c69bc |
| `50002` | 业务处理失败 / 50001:商品信息获取失败，请重试（sub_code: isv.business-failed:50001） | 50001:商品信息获取失败，请重试 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:30000",
  "sub_msg": "通用参数错误"
}
```

## 备注
