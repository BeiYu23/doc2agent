# inspection.operateInspectionReports

> 验机报告管理操作（绑定/解绑sku，上架/下架）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.operateInspectionReports` |
| 中文名 | 验机报告管理操作（绑定/解绑sku，上架/下架 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/operateInspectionReports` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8258 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operate_type` | body | mixed | 是 | 1：绑定；2：解绑；3：上架；4：下架；5：修改备注 | `1` |
| `operation_target_list` | body | array | 否 | 操作目标列表 | `` |
| `  └ remark` | body | string | 否 | 备注 | `备注` |
| `  └ inspection_report_id` | body | string | 是 | 验机报告id | `2046779466369208320` |
| `  └ sku_for_bind_list` | body | array | 否 | 仅在绑定/解绑场景需要传入 | `` |
| `    └ product_sku_id` | body | string | 否 | 商品sku_id | `3662510792962562` |
| `    └ product_id` | body | string | 否 | 商品product_id | `3815583939616178477` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/operateInspectionReports?app_key=your_appkey_here&method=inspection.operateInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数（如 operator_info , operator_info.operator_id , operation_target_list 不能为空）（sub_code: isv.missing-parameter:-41003） | 请检查并补充请求体中缺失的必传字段 |
| `40004` | 非法的参数 / 传入的参数非法或校验未通过（例如 operator_id 非法、获取验机报告详情失败、绑定SKU时 product_id 为空、或SKU与报告的类目/品牌/型号不匹配）（sub_code: isv.parameter-invalid:-41004） | 请根据具体错误提示核对绑定的 SKU ID 及其所属的商品和类目/型号信息是否合法 |
| `50002` | 业务处理失败 / 操作质检报告失败（sub_code: isv.business-failed:-41005） | 请检查操作数据是否正确，若重试仍失败请联系服务提供方 |
| `20000` | 系统错误 / 操作质检报告失败，服务返回为空（sub_code: isp.service-error:-41002） | 服务端内部异常，请稍后重试或联系服务提供方 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "inspection_report_operate_result_map": {}
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
  "sub_msg": "缺少必选参数（如 operator_info , operator_info.operator_id , operation_target_list 不能为空）"
}
```

## 备注
