# microapp.generateCombination

> 生成组合购

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.microapp.generateCombination` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/microapp/generateCombination` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2787 |
| 更新日期 | `2022-12-12` |

## 接口说明

- 文档书: 商品API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `title` | body | string | 是 | 当前生成组合购的标题，长度为6-10个字符 | `组合购标题` |
| `creator` | body | number | 是 | 操作者账号id，飞鸽客服场景下即飞鸽客服id | `11111` |
| `comment` | body | string | 否 | 卖家留言，用于展示在C端组件首页上 | `这是商品组合购` |
| `items` | body | array | 否 | 商品信息 | `` |
| `  └ product_id` | body | string | 是 | 商品id | `11` |
| `  └ sku_id` | body | string | 是 | sku id | `11` |
| `  └ sku_num` | body | number | 是 | sku数量 | `1` |
| `  └ price` | body | string | 否 | 价格 | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/syncV2?app_key=your_appkey_here&method=coupons.syncV2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `combo_link` | string | 生成的组合购短链接 | `https://v.douyin.com/dfadfsd` |
| `biz_error` | object | 返回错误 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:10001） | 系统错误，联系平台 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:10010） | 检查参数 |
| `40002` | 缺少必选参数 / 参数非法（sub_code: isv.missing-parameter:10011） | 检查参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:10012） | 请重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:10013） | 请重试 |
| `50002` | 业务处理失败 / 2010004:搭配名称不能超过10个字符（sub_code: isv.business-failed:2010004） | 检查搭配名称参数，6-10个字符之间 |
| `50002` | 业务处理失败 / 10014:商品数量不能为空（sub_code: isv.business-failed:10014） | 搭配商品数量不能为空 |
| `50002` | 业务处理失败 / 2010013:获取商品信息失败（sub_code: isv.business-failed:2010013） | 校验商品信息状态 |
| `50002` | 业务处理失败 / 10015:商品Sku非法（sub_code: isv.business-failed:10015） | 检查商品sku信息 |
| `50002` | 业务处理失败 / 2010001:系统异常,请重试（sub_code: isv.business-failed:2010001） | 2010001:系统异常,请重试 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10001",
  "sub_msg": "系统错误"
}
```

## 备注
