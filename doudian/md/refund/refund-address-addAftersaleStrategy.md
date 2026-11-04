# address.addAftersaleStrategy

> 添加售后地址策略

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.refund.address.addAftersaleStrategy` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/addAftersaleStrategy` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/17/6905 |
| 更新日期 | `2024-09-25` |

## 接口说明

- 文档书: 售后退款API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `aftersale_strategy` | body | object | 否 | 售后策略信息 | `` |
| `  └ to_add_product_id` | body | array | 否 | 非必传。添加策略时需绑定的商品ID列表，单次请求中不允超过100个商品ID。 | `[123344]` |
| `  └ strategy_type` | body | mixed | 否 | 必传。策略类型。静态策略类型和用户收货地址无关，只是将商品和退货地址绑定，无论消费者收货地址在哪里，该策略绑定的商品全部退往同一地址。动态策略类型绑定的商品可以指定不同的消费者收货区域退往不同的退货地址，比如指定消费者收货地址在北京、天津、河北的订单退往华北仓，指定消费者收货地址在山东、江苏的订单退往华东仓。静态类型策略和动态类型策略都可以绑定多个商品。 | `1-静态策略类型，2-动态策略类型。` |
| `  └ strategy_name` | body | string | 否 | 必传。策略名称，不允许超过10个字。 | `华东仓退货策略` |
| `  └ address` | body | array | 否 | 必传。售后策略绑定的地址列表， | `` |
| `    └ id` | body | mixed | 否 | 必传。商家通过抖店后台-订单管理-物流工具-地址库管理或者通过三方服务商平台在抖店后台创建地址生成的ID，可以通过接入/address/list获取商家地址列表。 | `101` |
| `    └ province_id` | body | mixed | 否 | 非必传。动态策略类型必传，静态策略类型不传。省ID，消费者收货地址对应的省ID，需要使用标准四级地址对应的省ID，通过/address/provinceList获取。 | `11` |
| `    └ city_id` | body | mixed | 否 | 非必传。动态策略类型必传，静态策略类型不传。城市ID，消费者收货地址对应的市ID，需要使用标准四级地址对应的市ID，通过/address/getAreasByProvince获取是ID。 | `110000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/addAftersaleStrategy?app_key=your_appkey_here&method=address.addAftersaleStrategy&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fail_product_list` | array | 绑定失败商品id列表 | `` |
| `success_product_list` | array | 绑定成功的商品ID; | `1233` |
| `strategy_id` | string | 策略ID; | `AFS1234` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 请输入正确的参数（sub_code: isv.parameter-invalid:4000） | 根据返回的错误信息提示，对传入参数做修改后重试。 |
| `50002` | 业务处理失败 / 已达到1000条新建策略上限，请删除不需要的策略后再添加（sub_code: isv.business-failed:100003） | 删除不再使用的策略，然后重新添加新的策略；或者联系抖店平台运营，提升单店铺创建策略数量的上限。 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:8000） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:7000） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 系统开小差了，请稍后重试（sub_code: isv.business-failed:3000） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:3001） | 一般为系统内部异常，重试不能解决后，可以在开放平台提工单或者联系抖店运营/开发人员解决 |
| `50002` | 业务处理失败 / 所选地址信息不完整，请前往「物流-地址库管理」重新编辑地址信息后重试（sub_code: isv.business-failed:100008） | 商家在三方平台或者抖店「订单-物流工具-地址库管理」对策略绑定的地址进行编辑修改 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_product_list": [
      {
        "fail_reason": "商品正在审核中，暂不支持修改",
        "product_id": "12233"
      }
    ],
    "strategy_id": "AFS1234",
    "success_product_list": "1233"
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
