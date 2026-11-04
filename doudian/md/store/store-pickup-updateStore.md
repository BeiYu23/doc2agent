# pickup.updateStore

> 更新门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.updateStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/updateStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7236 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_info` | body | object | 是 | 门店信息 | `` |
| `  └ city` | body | string | 是 | 市 | `上海市` |
| `  └ threshold` | body | mixed | 否 | 门店接单阈值 | `100` |
| `  └ contact` | body | string | 是 | 联系方式 | `13312341235` |
| `  └ name` | body | string | 是 | 门店名称 | `测试门店1` |
| `  └ store_code` | body | string | 是 | 门店编码 | `A1011` |
| `  └ district_code` | body | string | 是 | 区code | `310110` |
| `  └ street` | body | string | 否 | 4级地址 街道/镇 | `江浦路街道` |
| `  └ province` | body | string | 是 | 省 | `上海市` |
| `  └ city_code` | body | string | 是 | 城市code | `310000` |
| `  └ street_code` | body | string | 否 | 4级地址code | `310110008` |
| `  └ biz_type` | body | mixed | 是 | 业务类型 2:到店自提 | `2` |
| `  └ address` | body | string | 是 | 详细地址 | `江湾城路99号尚浦中心5号楼` |
| `  └ announcement` | body | string | 否 | 门店公告 | `正常营业` |
| `  └ province_code` | body | string | 是 | 省份code | `31` |
| `  └ store_id` | body | string | 是 | 门店ID | `1138991934` |
| `  └ latitude` | body | string | 否 | 维度 | `31.270755` |
| `  └ open_time` | body | object | 是 | 营业时间 | `` |
| `    └ day_map` | body | string | 是 | 1:周一、2:周一、3:周三、4:周四、5:周五、6:周六、7:周日  时间是空格分隔，比如08:30-11:00 13:00-17:00 | `{ "1": "08:00-20:00", "2": "08:00-20:00", "3": "08:00-20:00", "4": "08:00-20:00", "5": "08:00-20:00", "6": "08:00-20:00", "7": "08:00-20:00" }` |
| `    └ custom` | body | string | 否 | - | `-` |
| `  └ district` | body | string | 是 | 区 | `杨浦区` |
| `  └ longitude` | body | string | 否 | 经度 | `121.522797` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/updateStore?app_key=your_appkey_here&method=pickup.updateStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 状态码，0: 成功 | `0` |
| `msg` | string | 出错提示消息 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -3:当前操作类型不合法（sub_code: isv.business-failed:-3） | 操作类型非法 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "success"
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
  "sub_code": "isv.business-failed:-3",
  "sub_msg": "-3:当前操作类型不合法"
}
```

## 备注
