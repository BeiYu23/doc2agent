# shop.openUnbindShopInfo

> 店铺装修-解绑门店-门店信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.openUnbindShopInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/openUnbindShopInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6300 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tmp_id` | body | string | 是 | 页面id | `7332399246898888986` |
| `sort_type` | body | mixed | 否 | 时间排序方式 0：不排序 1：绑定时间从新到老 2：绑定时间从老到新 | `1` |
| `page_no` | body | mixed | 否 | 页码 | `1` |
| `page_size` | body | mixed | 否 | 一页个数 | `10` |
| `shop_name` | body | string | 否 | 模糊查询名称 | `店铺` |
| `page_status` | body | mixed | 否 | 门店状态（搜索用，仅有   PENDING = 1 //未生效， USING = 2 // 生效） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/openUnbindShopInfo?app_key=your_appkey_here&method=shop.openUnbindShopInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data_result` | array | 返回值 | `` |
| `page_result` | object | 页面参数 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / RPC调用失败（sub_code: isp.service-error:10004） | 根据报错内容排查 |

## 响应示例

成功：

```json
{
  "data": {
    "data_result": [
      {
        "bind_time": "1708423512",
        "describe": "1111",
        "operator": {
          "operator_id": "155749636",
          "operator_name": "系统",
          "shop_id": "155753860"
        },
        "shop_id": "155753860",
        "shop_name": "开放平台入驻资质免审测试01",
        "status": "1"
      }
    ],
    "page_result": {
      "page_no": "1",
      "page_size": "10",
      "total": "4"
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
  "sub_code": "isp.service-error:10004",
  "sub_msg": "RPC调用失败"
}
```

## 备注
