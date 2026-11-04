# product.setOnline

> 拍卖商品上架接口-仅限拍卖商品使用

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.setOnline` |
| 中文名 | 拍卖商品上架接口-仅限拍卖商品使用 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/setOnline` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/251 |
| 更新日期 | `2026-07-14` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品id | `355653216545615442145` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/setOnline?app_key=your_appkey_here&method=product.setOnline&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 【重复操作】商品操作重复，当前状态：上架（sub_code: isv.parameter-invalid:2010001） | 请重新选择商品 |
| `40004` | 非法的参数 / 商户状态不合法（sub_code: isv.parameter-invalid:10008） | 请检查店铺状态 |
| `50002` | 业务处理失败 / 获取店铺标签错误（sub_code: isv.business-failed:2010013） | 请检查店铺状态 |
| `50002` | 业务处理失败 / 获取类目信息失败（sub_code: isv.business-failed:2010005） | 检查参数后重试 |
| `50002` | 业务处理失败 / 因为店铺受到处置，限制发品，更多请到商家后台奖惩中心查看（sub_code: isv.business-failed:2010326） | 请检查店铺状态 |
| `50002` | 业务处理失败 / 缺少必要参数（sub_code: isv.business-failed:20024） | 请检查必填参数后重试 |
| `50002` | 业务处理失败 / 【重复操作】商品操作重复，当前状态：上架（sub_code: isv.business-failed:2010021） | 请检查商品状态 |
| `50002` | 业务处理失败 / 2010004:组合商品无法直接上线（sub_code: isv.business-failed:2010004） | 组合商品无法直接上线，请检查 |
| `50002` | 业务处理失败 / 2010050:由于您尚未进行店铺官方账号绑定，店铺部分功能不可用，当前无法发布或上架商品，请前往【店铺】-【店铺设置】-【店铺官方账号】页面完成绑定（sub_code: isv.business-failed:2010050） | 由于您尚未进行店铺官方账号绑定，店铺部分功能不可用，当前无法发布或上架商品，请前往【店铺】-【店铺设置】-【店铺官方账号】页面完成绑定 |
| `50002` | 业务处理失败 / 2010022:【状态非法】商品状态错误, 当前状态: 删除（sub_code: isv.business-failed:2010022） | 2010022:【状态非法】商品状态错误, 当前状态: 删除 |
| `50002` | 业务处理失败 / 110200024:发布当前类目商品，还需缴纳1983.37元保证金，点击“<a href='/ffa/content/shop_deposit' target="_blank">立即充值</a>”补全对应保证金后方可发布商品，详见<a href='https://school.jinritemai.com/doudian/web/article/101830?from=shop_table&btm_ppre=a4977.b4369.c0.d0&btm_pre=a4977.b6444.c0.d0&btm_（sub_code: isv.business-failed:110200024） | 110200024:发布当前类目商品，还需缴纳1983.37元保证金，点击“<a href='/ffa/content/shop_deposit' target="_blank">立即充值</a>”补全对应保证金后方可发布商品，详见<a href='https://school.jinritemai.com/doudian/web/article/101830?from=shop_table&btm_ppre=a4977.b4369.c0.d0&btm_pre=a4977.b6444.c0.d0&btm_ |
| `50002` | 业务处理失败 / 2010401:请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 2010401:请求被限流, 请稍后再试 |
| `50002` | 业务处理失败 / 110502062:移动电源缺少产品数字标识，无法上架。请编辑商品，在"产品数字标识"专区填写（sub_code: isv.business-failed:110502062） | 110502062:移动电源缺少产品数字标识，无法上架。请编辑商品，在"产品数字标识"专区填写 |
| `50002` | 业务处理失败 / 110320001:组合商品无法直接上线（sub_code: isv.business-failed:110320001） | 110320001:组合商品无法直接上线 |

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
  "sub_code": "isv.parameter-invalid:2010001",
  "sub_msg": "【重复操作】商品操作重复，当前状态：上架"
}
```

## 备注
