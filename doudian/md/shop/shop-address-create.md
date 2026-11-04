# address.create

> 创建店铺地址库

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.address.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1510 |
| 更新日期 | `2023-10-19` |

## 接口说明

- 文档书: 店铺API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `address` | body | object | 是 | 地址信息 | `` |
| `  └ user_name` | body | string | 是 | 联系人姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 手机号码 | `18012345678` |
| `  └ province_id` | body | number | 是 | 省份ID | `32` |
| `  └ city_id` | body | number | 是 | 城市ID | `330700` |
| `  └ town_id` | body | number | 是 | 区ID | `330782` |
| `  └ detail` | body | string | 是 | 详细地址 | `xxxxx` |
| `  └ street_id` | body | number | 是 | 街道ID | `330782003` |
| `  └ link_type` | body | string | 是 | 联系方式类型(0-手机,1-普通座机,2-企业座机) | `0-手机,1-普通座机,2-企业座机` |
| `  └ fixed_phone` | body | string | 否 | 普通座机格式：区号-座机号-分机号(分机号选填)、区号3~4位、座机号7~8位、分机号不超过5位。企业座机：400/800开头不超过10位、95开头在5~8we | `普通座机：400-12345678-1234，企业座机：40012345` |
| `  └ remark` | body | string | 否 | 售后备注，限制200字符 | `拒收到付` |
| `store_id` | body | number | 否 | 门店ID（新建地址绑定在该门店下，非门店场景无需填写） | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `address_id` | number | 新建地址ID | `10000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 已达到50条新建地址上限（sub_code: isv.parameter-invalid:100003） | 删除多余 |
| `40004` | 非法的参数 / 已有对应的记录:${address_id}（sub_code: isv.parameter-invalid:100002） | 可获取错误信息中已存在的address_id |
| `40004` | 非法的参数 / 系统繁忙，请稍后重试（sub_code: isv.parameter-invalid:6000） | 系统繁忙，请稍后重试 |
| `40004` | 非法的参数 / 联系人不能超过32字（sub_code: isv.parameter-invalid:4000） | 请修改联系人信息 |
| `50002` | 业务处理失败 / 操作过于频繁，请稍后重试（sub_code: isv.business-failed:100001） | 操作过于频繁，请稍后重试 |
| `50002` | 业务处理失败 / 暂不支持该区号（sub_code: isv.business-failed:100009） | 暂不支持该区号 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:5001） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 4002:地址详细信息中存在冗余内容【(开了扣眼修改过吊牌损坏以及穿过洗过等影响二次销售不予退换货)转】，需将地址详细信息精简为【暄悦东街24号1楼T2】后再重新提交（sub_code: isv.business-failed:4002） | 4002:地址详细信息中存在冗余内容【(开了扣眼修改过吊牌损坏以及穿过洗过等影响二次销售不予退换货)转】，需将地址详细信息精简为【暄悦东街24号1楼T2】后再重新提交 |
| `50002` | 业务处理失败 / 4001:当前输入的地址未精确到村、组、门牌号、楼栋、支路等，请核查修改后提交。（sub_code: isv.business-failed:4001） | 4001:当前输入的地址未精确到村、组、门牌号、楼栋、支路等，请核查修改后提交。 |

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
  "sub_code": "isv.parameter-invalid:100003",
  "sub_msg": "已达到50条新建地址上限"
}
```

## 备注
