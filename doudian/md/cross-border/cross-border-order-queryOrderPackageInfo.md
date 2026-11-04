# 查询店铺单包裹信息

> order.queryOrderPackageInfo — 查询店铺单包裹信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询店铺单包裹信息 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-order-queryOrderPackageInfo` |
| 接口 ID | `doudian.cross-border.order.queryOrderPackageInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/queryOrderPackageInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6212 |
| 更新日期 | `2024-02-29` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_id` | body | string | 是 | 订单id | `6496679971677798670` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/queryOrderPackageInfo?app_key=your_appkey_here&method=order.queryOrderPackageInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_package_info` | object | 订单包裹信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 查询订单数据为空（sub_code: isv.parameter-invalid:201） | 请检查订单号是否正确 |
| `20000` | 系统错误 / 调用下游接口失败（sub_code: isp.service-error:503） | 稍后重试 |
| `20001` | 内部服务超时 / 服务超时（sub_code: isp.service-timeout-error:1204） | 服务超时，请稍后重试 |
| `20000` | 系统错误 / 内部处理失败（sub_code: isp.service-error:505） | 稍后重试 |
| `40002` | 缺少必选参数 / 请求参数不完整或不合法（sub_code: isv.missing-parameter:501） | 请修改入参后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "order_package_info": {
      "is_multi_package": "true",
      "order_status": "3",
      "package_info": [
        {
          "delivery_info": [
            {
              "company_info": {
                "company_name": "中通快递",
                "express_company": "zhongtong",
                "express_no": "75530132493095",
                "icon": "https://XXXX",
                "telephone": "400-XXX-XXXX",
                "url": "www.zto.cn"
              },
              "create_time": "1708633805",
              "deliver_id": "7338402565379522860",
              "deliver_type": "0",
              "track_info": [
                {
                  "context": "包裹已完成出库，来自【XXX仓】",
                  "site": "北京",
                  "state": "122",
                  "state_desc": "仓库处理中",
                  "time_stamp": "1708659849"
                }
              ],
              "track_no": "75530132493095"
            }
          ],
          "is_complement_deliver": "true",
          "product_info": [
            {
              "actual_sub_sku": [
                {
                  "is_free": "true",
                  "num": "3",
                  "product_id": "3520562294461467745",
                  "product_name": "XX行李箱",
                  "sku_id": "1719024557525047",
                  "sku_img": "https:xxxx"
                }
              ],
              "is_free": "false",
              "num": "5",
              "product_id": "3520562294461467745",
              "product_name": "XX行李箱",
              "sku_id": "3254535",
              "sku_img": "https:xxxx",
              "sku_order_id": "4781320682406083640",
              "sub_sku_desc": [
                {
                  "product_id": "3520562294461467745",
                  "sku_id": "1719024557525047",
                  "unit_num": "3"
                }
              ]
            }
          ],
          "send_type": "1",
          "track_state": "1"
        }
      ],
      "shop_id": "94956",
      "shop_order_id": "6917533224570258991",
      "wait_send_product_info": {
        "delivery_info": [
          {
            "company_info": {
              "company_name": "中通快递",
              "express_company": "zhongtong",
              "express_no": "75530132493095",
              "icon": "https://XXXX",
              "telephone": "400-XXX-XXXX",
              "url": "www.zto.cn"
            },
            "create_time": "1708633805",
            "deliver_id": "7338402565379522860",
            "deliver_type": "0",
            "track_info": [
              {
                "context": "包裹已完成出库，来自【XXX仓】",
                "site": "北京",
                "state": "122",
                "state_desc": "仓库处理中",
                "time_stamp": "1708659849"
              }
            ],
            "track_no": "75530132493095"
          }
        ],
        "product_info": [
          {
            "actual_sub_sku": [
              {
                "is_free": "true",
                "num": "1",
                "product_id": "3520562294461467753",
                "product_name": "XX衣服",
                "sku_id": "4781320682406083640",
                "sku_img": "https:xxxx"
              }
            ],
            "is_free": "true",
            "num": "3",
            "product_id": "3473196049974326153",
            "product_name": "XX鞋子",
            "sku_id": "3254535",
            "sku_img": "https:xxxx",
            "sku_order_id": "4781320682406083640",
            "sub_sku_desc": [
              {
                "product_id": "3520562294461467745",
                "sku_id": "1719024557525047",
                "unit_num": "3"
              }
            ]
          }
        ]
      }
    }
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
  "sub_code": "isv.parameter-invalid:201",
  "sub_msg": "查询订单数据为空"
}
```

## 备注
