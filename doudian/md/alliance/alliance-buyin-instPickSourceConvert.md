# buyin.instPickSourceConvert

> 商品选品来源转链

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.instPickSourceConvert` |
| 中文名 | 商品选品来源转链 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/instPickSourceConvert` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1454 |
| 更新日期 | `2023-04-23` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_url` | body | string | 是 | 商品链接 | `https://haohuo.jinritemai.com/views/product/item2?id=35119804196108` |
| `pick_extra` | body | string | 否 | 自定义参数（只允许 数字、字母和 _，限制长度为20） | `dsds_2ew` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/instPickSourceConvert?app_key=your_appkey_here&method=buyin.instPickSourceConvert&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `40004` | 非法的参数 / 无效商品URL（sub_code: isv.parameter-invalid:1056） | 无效商品URL |
| `40004` | 非法的参数 / 商品没有加入精选联盟（sub_code: isv.parameter-invalid:4133） | 商品没有加入精选联盟 |
| `40004` | 非法的参数 / 获取商品信息失败（sub_code: isv.parameter-invalid:4125） | 获取商品信息失败 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "product_url": "https://haohuo.jinritemai.com/views/product/item2?id=35119804196108&pick_source=R9AhDER"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
