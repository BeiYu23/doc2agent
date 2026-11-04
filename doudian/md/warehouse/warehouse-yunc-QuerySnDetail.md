# yunc.QuerySnDetail

> 查询sn码细节

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.QuerySnDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/QuerySnDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/8064 |
| 更新日期 | `2026-03-10` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_order_no` | body | string | 否 | ERP单号 | `"1111"` |
| `page_no` | body | mixed | 否 | 分页查询当前页，默认值1 | `1` |
| `page_size` | body | mixed | 否 | 分页查询每页数量，默认值10 | `10` |
| `cargo_code` | body | string | 否 | 货品id | `"11111"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/QuerySnDetail?app_key=your_appkey_here&method=yunc.QuerySnDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 响应数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 货品不存在（sub_code: isv.business-failed:62302630） | 货品信息校验不通过，按提示修改 |
| `20001` | 内部服务超时 / 1103:请求内部服务超时（sub_code: isp.service-timeout-error:1103） | 请重试 |
| `50002` | 业务处理失败 / 1003:请求内部服务异常,请重试（sub_code: isv.business-failed:1003） | 请重试 |
| `50002` | 业务处理失败 / 1100:查询店铺与货主绑定关系失败，请重试！（sub_code: isv.business-failed:1100） | 查询店铺与货主绑定关系失败，请重试！ |
| `50002` | 业务处理失败 / 1253:货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！（sub_code: isv.business-failed:1253） | 货主和店铺绑定关系不存在，请在scm进行货主和店铺关系绑定后重推数据！ |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "page": "1",
      "page_size": "10",
      "sn_list": [
        {
          "cargo_code": "1",
          "sn": "11111",
          "sn_status": "1",
          "sn_status_desc": "使用"
        }
      ],
      "total": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:62302630",
  "sub_msg": "货品不存在"
}
```

## 备注
