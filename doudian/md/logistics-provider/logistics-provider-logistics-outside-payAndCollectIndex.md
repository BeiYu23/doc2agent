# logistics.outside.payAndCollectIndex

> 按照服务商、揽收地区、收货地区查询各服务商全国或各省份流向上Top200的责任线路以及对应的责任运单量

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.outside.payAndCollectIndex` |
| 中文名 | 按照服务商 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2926 |
| 更新日期 | `2023-02-03` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | number | 是 | 开始秒级时间戳 | `1675353599` |
| `end_time` | body | number | 是 | 结束秒级时间戳 | `1675353599` |
| `fresh_type` | body | number | 是 | 生鲜类型 0 表示非生鲜 1 表示生鲜 2 表示全部 | `0` |
| `date_type` | body | number | 是 | 日期类型  1 自然日 2 自然周 3 自然月 4 自定义 | `1` |
| `area` | body | object | 是 | 发货地区 | `` |
| `  └ code` | body | string | 否 | 地区code | `11` |
| `  └ area_type` | body | number | 是 | 发货地区类型 1 全国 2 省份 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/inbound/create?app_key=your_appkey_here&method=yunc.wms.inbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回的数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 领航者查询错误（sub_code: isv.business-failed:101） | 对外物流指数 |
| `50002` | 业务处理失败 / 查询时间范围过长（sub_code: isv.business-failed:10004） | 对外物流指数 |
| `40004` | 非法的参数 / 查询生鲜维度类型异常（sub_code: isv.parameter-invalid:10005） | 对外物流指数 |
| `40004` | 非法的参数 / 查询日期类型异常（sub_code: isv.parameter-invalid:10006） | 对外物流指数 |
| `40004` | 非法的参数 / 查询地区类型异常（sub_code: isv.parameter-invalid:10008） | 对外物流指数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "sub_code": "isv.business-failed:101",
  "sub_msg": "领航者查询错误"
}
```

## 备注
