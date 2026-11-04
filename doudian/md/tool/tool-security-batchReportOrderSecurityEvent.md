# security.batchReportOrderSecurityEvent

> 电商云批量上报订单安全事件接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.security.batchReportOrderSecurityEvent` |
| 中文名 | 电商云批量上报订单安全事件 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/security/batchReportOrderSecurityEvent` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/1655 |
| 更新日期 | `2022-12-12` |

## 接口说明

- 文档书: 工具API（版本 V5.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `event_type` | body | string | 是 | 订单事件类型 1:订单访问事件, 2:订单流出事件 | `1` |
| `events` | body | array | 是 | 订单事件列表 | `` |
| `  └ event_id` | body | string | 是 | HTTP 请求头里的 doudian-event-id 对应的值 | `"1649843080000603"` |
| `  └ account_id` | body | string | 是 | 商户的账户ID，每个ISV下需要保证唯一。独立生成的账户唯一标识 | `"101234567"` |
| `  └ account_type` | body | string | 是 | main_account 服务商账号体系中的主账号、子账号 main_account/sub_account | `"main_account"` |
| `  └ order_related_shop_id` | body | string | 是 | orderIds 实际归属的店铺id | `"10001"` |
| `  └ shop_ids` | body | array | 否 | 选填 ，account_id 关联的店铺 ID 列表 | `["1","2","3"]` |
| `  └ order_ids` | body | array | 是 | 订单 ids, 单次最大数量 50, 超过 50 需分批上传 | `["111","222","333"]` |
| `  └ operation_type` | body | string | 是 | 操作类型.支持操作类型:      1:view_order (查看订单)      2:view_order_list (查看订单列表)      3:download_order (下载订单)      4:download_order_list (下载订单列表)      5:print_order (打印订单)      6:print_order_list (打印订单列表)      7:export_order (导出订单)      8:export_order_list (导出订单列表)      9:delete_order (删除订单) | `1` |
| `  └ operate_time` | body | string | 是 | 精确到秒的操作时间戳，格林威治时间，如1522555200 | `"1522555200"` |
| `  └ url` | body | string | 是 | isv请求url | `"/torder/check"` |
| `  └ ip` | body | string | 是 | 客户端IP，须为用户操作时真实客户端外网IP 若使用SLB，客户端IP添加在HTTP请求的X-Forwarded-For末尾；若使用CWAF，客户端IP放在 X-Real-Ip 属性 | `"42.120.74.21"` |
| `  └ mac` | body | string | 否 | 登录设备的mac地址 | `"5489-98f6-16c0"` |
| `  └ identify_info_list` | body | array | 是 | 对外发送的订单信息明细格式 场景:商家来调解密接口，同时解密接口里面包含了敏感信息 | `` |
| `    └ name` | body | string | 是 | 代表订单某个信息的字段名 (可直接取抖店开放平台返回的订单信息中的字段名) | `orderId` |
| `    └ encrypted` | body | boolean | 是 | 代表此字段在发送给第三方时是否为加密状态 | `false` |
| `  └ device_type` | body | string | 否 | iOS / Android / Windows	商户在什么设备上使用 ISV 的软件 | `"iOS"` |
| `  └ device_id` | body | string | 否 | 设备id，标识唯一设备 | `"12345"` |
| `  └ referer` | body | string | 是 | HTTP 请求头里referer对应的值,参考链接 | `"https://www.abc.com/"` |
| `  └ user_agent` | body | string | 否 | HTTP 请求头里的 userAgent对应的值 | `"Mozilla/5.0"` |
| `  └ purchase_product_info_list` | body | array | 否 | 采购商品信息 | `` |
| `    └ purchase_platform_type` | body | string | 否 | 采购平台，枚举值如下：1、拼多多，2、淘宝，3、1688，4、其他，5、淘特，6、天猫，7、京东，8、快手，9、小红书，10、得物，11、苏宁，12、抖音 | `1` |
| `    └ purchase_product_url` | body | string | 否 | 采购商品链接 | `"https://www.abc.com/"` |
| `    └ external_purchaser_id` | body | string | 否 | 采购人id（外部） | `"12345"` |
| `    └ product_name` | body | string | 否 | 本平台订单的商品名称 | `"商品名"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `CustomError` | object | 错误信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不正确（sub_code: isv.parameter-invalid:602） | 请检查入参 |
| `20000` | 系统错误 / 100:服务器错误（sub_code: isp.service-error:100） | 重试 |

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
  "sub_code": "isv.parameter-invalid:602",
  "sub_msg": "参数不正确"
}
```

## 备注
