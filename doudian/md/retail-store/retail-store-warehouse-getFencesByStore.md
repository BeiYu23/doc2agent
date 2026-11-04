# 根据门店查询围栏

> warehouse.getFencesByStore — 根据门店查询围栏

| 元信息 | 值 |
| --- | --- |
| 中文名 | 根据门店查询围栏 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-warehouse-getFencesByStore` |
| 接口 ID | `doudian.retail-store.warehouse.getFencesByStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/getFencesByStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/6374 |
| 更新日期 | `2024-08-20` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id_list` | body | array | 是 | 门店ID列表，最多一次传20个 | `123345,12333332` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/getFencesByStore?app_key=your_appkey_here&method=warehouse.getFencesByStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `fence_map` | string | key为门店ID，value为围栏详细内容 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2122） | 修改后重试 |
| `20000` | 系统错误（sub_code: isp.service-error:2129999） | 重试 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2121006） | 根据返回内容判断 |
| `50002` | 业务处理失败 / 获取相关数据失败（sub_code: isv.business-failed:212000264） | 根据返回内容判断 |

## 响应示例

成功：

```json
{
  "data": {
    "fence_map": {}
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
  "sub_code": "isv.parameter-invalid:2122",
  "sub_msg": "参数错误"
}
```

## 备注
