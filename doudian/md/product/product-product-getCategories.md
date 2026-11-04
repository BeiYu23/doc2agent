# product.getCategories

> 获取商家可选类目

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.getCategories` |
| 中文名 | 获取商家可选类目 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/getCategories` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4649 |
| 更新日期 | `2026-01-21` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `id` | body | mixed | 是 | 父类目id，传0可以获取一级类目 | `0` |
| `channel` | body | mixed | 否 | 类目渠道，0：门捷列夫类目，1:标准类目；若不传入，当id=0时，由类目服务内部自行开关控制：0:默认查询门捷列夫类目；1:获取商家灰度标，跟随大盘灰度节奏切换；2:默认查询标准类目 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/getCategories?app_key=your_appkey_here&method=product.getCategories&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `category_list` | array | 父类目本身信息以及子类目信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:2012004） | 请检查参数后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:2010001） | 请检查参数后重试 |
| `20000` | 系统错误 / 读取失败（sub_code: isp.service-error:2010013） | 重试 |
| `50002` | 业务处理失败 / 2012001:获取商家信息失败（sub_code: isv.business-failed:2012001） | 2012001:获取商家信息失败 |
| `50002` | 业务处理失败 / 读取失败（sub_code: isv.business-failed:2012013） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "category_list": [
      {
        "channel": "0",
        "id": "20000",
        "is_leaf": "false",
        "level": "1",
        "name": "类目名称",
        "parent_id": "0"
      }
    ]
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
  "sub_code": "isv.parameter-invalid:2012004",
  "sub_msg": "非法的参数"
}
```

## 备注
