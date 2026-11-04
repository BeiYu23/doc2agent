# address.updateAftersaleStrategy

> 更新地址策略

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.address.updateAftersaleStrategy` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/updateAftersaleStrategy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6910 |
| 更新日期 | `2024-10-08` |

## 接口说明

- 文档书: 售后退款API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_strategy` | body | object | 否 | 售后策略; | `` |
| `  └ strategy_type` | body | mixed | 否 | 必传。策略类型。静态策略类型和用户收货地址无关，只是将商品和退货地址绑定，无论消费者收货地址在哪里，该策略绑定的商品全部退往同一地址。动态策略类型绑定的商品可以指定不同的消费者收货区域退往不同的退货地址，比如指定消费者收货地址在北京、天津、河北的订单退往华北仓，指定消费者收货地址在山东、江苏的订单退往华东仓。静态类型策略和动态类型策略都可以绑定多个商品。 | `1` |
| `  └ strategy_id` | body | string | 否 | 必传，策略id，需要更改的策略ID。 | `AFS7418493389946110223` |
| `  └ address` | body | array | 否 | 售后策略绑定的地址列表; | `` |
| `    └ city_id` | body | mixed | 否 | 非必传，消费者收货地址的市ID。如果operation=0，并且是动态退货策略，则必传；如果是operation=0，但是是静态策略，不是必传。 | `110000` |
| `    └ province_id` | body | mixed | 否 | 非必传，省ID。如果operation=0，并且是动态退货策略，则必传；如果是operation=0，但是是静态策略，不是必传。通过/address/getAreasByProvince获取是ID。 | `11` |
| `    └ id` | body | mixed | 否 | 非必传，地址ID。商家通过抖店后台-订单管理-物流工具-地址库管理或者通过三方服务商平台在抖店后台创建地址生成的ID，可以通过接入/address/list获取商家地址列表。如果是operation=0，则必传。通过/address/provinceList获取。 | `地址ID` |
| `  └ strategy_name` | body | string | 否 | 策略名称，不能超过10个字。 | `新的策略名称` |
| `  └ to_add_product_id` | body | array | 否 | 需绑定的商品列表 | `[3709205448604385763]` |
| `  └ to_del_product_id` | body | array | 否 | 需解绑的商品列表 | `[3709080842971250761]` |
| `operation` | body | mixed | 否 | 操作类型，必传。0-全覆盖地址策略，会用传递过来的请求中的信息覆盖已有的信息；1-只是增加绑定商品；2-只是删除绑定商品。 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/updateAftersaleStrategy?app_key=your_appkey_here&method=address.updateAftersaleStrategy&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_add_product_list` | array | 成功添加的商品ID列表; | `["3709080842971250761"]` |
| `success_del_product_list` | array | 成功删除的商品ID列表; | `["3709069364713095169"]` |
| `fail_add_product_list` | array | 添加失败的商品ID列表; | `` |
| `fail_del_product_list` | array | 添加失败的商品ID列表; | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请输入正确的参数（sub_code: isv.parameter-invalid:4000） | 根据返回的错误信息，调整参数后重试；如果重试无法成功，可以向抖店咨询。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3000） | 重试，如果一直报错，可以向抖店寻求帮助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3001） | 重试，如果一直报错，可以向抖店寻求帮助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 重试，如果一直报错，可以向抖店寻求帮助。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:7000） | 重试，如果一直报错，可以向抖店寻求帮助。 |
| `50002` | 业务处理失败 / 所选地址信息不完整，请前往「物流-地址库管理」重新编辑地址信息后重试（sub_code: isv.business-failed:100008） | 商家在三方平台或者抖店「订单-物流工具-地址库管理」对策略绑定的地址进行编辑修改。 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_add_product_list": [
      {
        "fail_code": "10001",
        "fail_reason": "系统更新失败",
        "product_id": "3708870048258064673"
      }
    ],
    "fail_del_product_list": [
      {
        "fail_code": "10002",
        "fail_reason": "商品正在审核中，禁止操作",
        "product_id": "3709239428372365627"
      }
    ],
    "success_add_product_list": "[\"3709080842971250761\"]",
    "success_del_product_list": "[\"3709069364713095169\"]"
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
  "sub_code": "isv.parameter-invalid:4000",
  "sub_msg": "请输入正确的参数"
}
```

## 备注
