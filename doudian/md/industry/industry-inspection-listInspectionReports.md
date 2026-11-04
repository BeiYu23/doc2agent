# inspection.listInspectionReports

> 验机报告列表页查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.listInspectionReports` |
| 中文名 | 验机报告列表页查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/listInspectionReports` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8257 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | mixed | 否 | 状态查询 | `` |
| `imei_list` | body | array | 否 | IMEI | `` |
| `product_id_list` | body | array | 否 | 商品 ID 列表 | `` |
| `product_name` | body | string | 否 | 商品名称 | `` |
| `remark` | body | string | 否 | 备注 | `` |
| `brand_id_list` | body | array | 否 | 品牌 ID 列表 | `` |
| `model_id_list` | body | array | 否 | 型号 ID 列表 | `` |
| `create_time_begin` | body | mixed | 否 | 创建时间范围 - 起始（包含） | `` |
| `inspection_report_id_list` | body | array | 否 | 验机报告 ID 列表 | `` |
| `create_time_end` | body | mixed | 否 | 创建时间范围 - 截止（包含） | `` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 每页大小 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/listInspectionReports?app_key=your_appkey_here&method=inspection.listInspectionReports&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数 (如：operator_info 身份信息为空 或 operator_id 为空)（sub_code: isv.missing-parameter:-41003） | 请检查并传入必传参数 operator_info.operator_id |
| `40004` | 非法的参数 / 非法的参数 (如：分页参数 page 小于等于 0，或 page_size 不在 1~100 之间)（sub_code: isv.parameter-invalid:-41004） | 请检查并修正分页参数，确保 page > 0 且 0 < page_size <= 100 |
| `50002` | 业务处理失败 / 业务处理失败 (如：获取质检报告列表失败)（sub_code: isv.business-failed:-41005） | 请检查查询条件参数的有效性，或稍后重试 |
| `20000` | 系统错误 / 服务不可用 (如：获取质检报告列表失败，底层服务返回为空)（sub_code: isp.service-error:-41002） | 系统内部繁忙或异常，请稍后重试 |

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
            "brand_id": "559043",
            "brand_name": "APPLE/苹果",
            "category_id": "1000007628",
            "category_name": "",
            "collection_code": "7457180029220159759_152",
            "cover_image": {
              "appearance_image_type": "10",
              "url": "xx"
            },
            "create_time": "1777278818",
            "fineness": "未拆封",
            "imei": "123451234512345",
            "inspection_report_id": "2048681961564306432",
            "model_id": "559043",
            "model_name": "iPhone 17 Pro Max",
            "qc_code": "QC763335335436204111",
            "reject_reason": "",
            "reject_time": "-62135596800",
            "remark": "xx",
            "shop_id": "111111",
            "status": "20",
            "std_category_id": "",
            "std_category_name": ""
          },
          "bound_product_list": [
            {
              "check_status": "3",
              "image_url": "xx",
              "product_id": "3816660039192674753",
              "product_name": "未拆封 Apple/苹果",
              "sku_list": [
                {
                  "sku_id": "3665335149822978",
                  "sku_name": "绿色/1GB+16GB",
                  "sku_price": "10000",
                  "spec_id": "1863605308847175"
                }
              ],
              "status": "0"
            }
          ]
        }
      ],
      "status_count_map": {},
      "total": "25"
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
  "sub_msg": "缺少必选参数 (如：operator_info 身份信息为空 或 operator_id 为空)"
}
```

## 备注
