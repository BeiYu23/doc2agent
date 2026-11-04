# crossborder.stockTransform

> 库存类型变动回告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossborder.stockTransform` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/stockTransform` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/918 |
| 更新日期 | `2023-05-19` |

## 接口说明

- 文档书: 跨境API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `transform_type` | body | number | 是 | 库存变动类型 1：良转次 2：次转良 | `1` |
| `vendor` | body | string | 是 | 服务商编码 | `GZJS` |
| `warehouse_code` | body | string | 是 | 服务商仓库编码 | `JSBBC01` |
| `shop_id` | body | number | 否 | 店铺id | `4321` |
| `occurrence_time` | body | number | 是 | 库存类型变动时间戳 单位：s | `123456789` |
| `remark` | body | string | 否 | 备注 | `备注` |
| `stock_transform_details` | body | array | 是 | 货品类型变动信息 | `` |
| `  └ cargo_code` | body | string | 是 | 货品编码 | `6543` |
| `  └ from_grade` | body | number | 是 | 调整前质量等级 1:良品 2:次品 | `1` |
| `  └ to_grade` | body | number | 是 | 调整后质量等级 1:良品 2:次品 | `2` |
| `  └ quantity` | body | string | 是 | 调整数量 | `10` |
| `  └ reason_code` | body | number | 是 | 调整原因编码 1：其他 | `1` |
| `  └ reason_msg` | body | string | 否 | 具体原因信息 | `具体原因` |
| `  └ extend` | body | string | 否 | 扩展信息 | `{"key":"value"}` |
| `  └ duty` | body | string | 否 | 责任方   "1"-服务商原因   "2"-商家原因 | `1` |
| `  └ remark` | body | string | 否 | 备注 | `测试` |
| `  └ evidence` | body | array | 否 | 证明材料 | `[]` |
| `idempotent_no` | body | string | 否 | 幂等号（建议传入，由调用方生成唯一ID，以防接口调用重试场景重复操作库存） | `1234` |
| `status` | body | number | 否 | 状态 2-待审核 1-已完成 5-已取消 | `2` |
| `inbound_plan_no` | body | string | 否 | 预约到货单号 | `123` |
| `adjust_biz_type` | body | string | 否 | 业务场景  201 库内商品正转残 202 库内商品残转正 203 库存批次属性转移 204 库内商品过期转残 | `201` |
| `owner_id` | body | number | 否 | 货主id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/stockTransform?app_key=your_appkey_here&method=crossborder.stockTransform&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 响应状态码 | `0` |
| `msg` | string | 响应状态信息 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 幂等调用异常（sub_code: isv.parameter-invalid:1007） | 请使用唯一幂等键 |
| `50002` | 业务处理失败 / 1005:接口调用异常，请重试，多次失败请人工反馈（sub_code: isv.business-failed:1005） | 请稍后重试 |
| `50002` | 业务处理失败 / 9001:调用货品中心有误（sub_code: isv.business-failed:9001） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1007",
  "sub_msg": "幂等调用异常"
}
```

## 备注
