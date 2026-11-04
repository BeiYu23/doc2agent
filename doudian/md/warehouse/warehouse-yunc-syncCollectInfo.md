# yunc.syncCollectInfo

> 货品数据采集接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.syncCollectInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/syncCollectInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2159 |
| 更新日期 | `2025-12-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `W001` |
| `cargo_code` | body | string | 是 | 货品编码 | `12345` |
| `owner_code` | body | string | 是 | 货主编码 | `12345` |
| `weight` | body | mixed | 否 | 单品重量，单位为g；(为空)或(>=0且<=50000)； | `10` |
| `length` | body | mixed | 否 | 单品长，单位为cm；(为空)或(>=0且<=1000)； | `10` |
| `width` | body | mixed | 否 | 单品宽，单位为cm；(为空)或(>=0且<=1000)； | `10` |
| `height` | body | mixed | 否 | 单品高，单位为cm；(为空)或(>=0且<=1000)； | `10` |
| `carton_list` | body | array | 否 | 箱规列表 | `` |
| `  └ carton` | body | string | 否 | 采购箱规，"单位为件；(为空)或(>=0且<=10000)； 保留2位小数； | `1` |
| `  └ carton_weight` | body | mixed | 否 | 箱规重量，单位为g；(为空)或(>=0且<=50000)； | `11` |
| `  └ carton_length` | body | mixed | 否 | 箱规长，单位为cm；(为空)或(>=0且<=1000)； | `11` |
| `  └ carton_width` | body | mixed | 否 | 箱规宽，单位为cm；(为空)或(>=0且<=1000)； | `11` |
| `  └ carton_height` | body | mixed | 否 | 箱规高，单位为cm；(为空)或(>=0且<=1000)； | `11` |
| `  └ loading_standard` | body | string | 否 | 装盘标准，"表示一个托盘上放置的采购箱规下的箱数； (为空)或(>=0且<=10000)； 保留2位小数； | `11` |
| `  └ carton_picture_list` | body | array | 否 | 单品净重图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `update_time` | body | mixed | 是 | 更新时间 | `1657000467` |
| `expiry_date` | body | mixed | 否 | 货品保质期，单位为天；(为空)或(>=0且<=36500)； | `100` |
| `weight_picture_list` | body | array | 否 | 单品重量图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `length_picture_list` | body | array | 否 | 单品长图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `width_picture_list` | body | array | 否 | 单品宽图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `height_picture_list` | body | array | 否 | 单品高图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `expiry_date_picture_list` | body | array | 否 | 货品保质期图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `net_weight` | body | mixed | 否 | 单位为g；(为空)或(>=0且<=50000)； 指货品的净重； | `11` |
| `net_weight_picture_list` | body | array | 否 | 单品净重图片列表 | `["http://xxxx1", "http://xxxx2"]` |
| `barcode_info_list` | body | array | 否 | 条码信息列表 | `` |
| `  └ barcode` | body | string | 否 | 条码 | `1234` |
| `  └ barcode_picture` | body | string | 否 | 条码图片 | `http://xxxx1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/syncCollectInfo?app_key=your_appkey_here&method=yunc.syncCollectInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 错误code | `0` |
| `msg` | string | 错误信息 | `成功` |
| `data` | mixed | 结构体 | `""` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数（sub_code: isv.missing-parameter:1001） | 根据错误提示信息修改 |
| `50002` | 业务处理失败 / 鉴权失败（sub_code: isv.business-failed:1003） | 鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "\"\"",
    "msg": "成功"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:1001",
  "sub_msg": "缺少必选参数"
}
```

## 备注
