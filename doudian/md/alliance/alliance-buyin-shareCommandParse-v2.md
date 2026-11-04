# buyin.shareCommandParse.v2

> 商品口令转商品解析

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.shareCommandParse.v2` |
| 中文名 | 商品口令转商品解析 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/shareCommandParse/v2` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/6469 |
| 更新日期 | `2026-09-29` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `command` | body | string | 是 | 抖音口令（仅商品口令） | `0:/ 长按鍑[旺柴]➕ 此条消息，咑[偷笑]剀ɒ[加油]，查看商品详情ÊÊqmg6uF7qnZFq8▽▽\t##qmguF79nZFq8##` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/shareCommandParse/v2?app_key=your_appkey_here&method=buyin.shareCommandParse.v2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_info` | object | 商品信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:256） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:255） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 非联盟商品（sub_code: isv.business-failed:4172） | 非联盟商品 |
| `50002` | 业务处理失败 / 无效商品口令（sub_code: isv.business-failed:4171） | 无效商品口令 |
| `50002` | 业务处理失败 / 亲爱的用户，因服务器升级，商品展示可能异常，带来不便，敬请见谅。（sub_code: isv.business-failed:8193） | 亲爱的用户，因服务器升级，商品展示可能异常，带来不便，敬请见谅。 |

## 响应示例

成功：

```json
{
  "data": {
    "product_info": {
      "cos_fee": "1",
      "cos_ratio": "10",
      "detail_url": "https://haohuo.jinritemai.com/views/product/item2?id=3400312511185213726",
      "product_id": "1234567",
      "promotable": "true",
      "title": "测试商品"
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
  "sub_code": "isv.parameter-invalid:256",
  "sub_msg": "参数校验失败"
}
```

## 备注
