# pickup.batchCreateStore

> 批量创建门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.batchCreateStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/batchCreateStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7233 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_info_list` | body | array | 是 | 门店信息列表，最大数量100 | `` |
| `  └ announcement` | body | string | 否 | 门店公告 | `正常营业` |
| `  └ address` | body | string | 是 | 详细地址 | `江湾城路95号` |
| `  └ contact` | body | string | 是 | 联系方式 | `19812122322` |
| `  └ district` | body | string | 是 | 区 | `杨浦区` |
| `  └ province` | body | string | 是 | 省 | `上海市` |
| `  └ district_code` | body | string | 否 | 区code | `-` |
| `  └ city_code` | body | string | 否 | 城市code | `-` |
| `  └ street` | body | string | 否 | 4级地址 街道/镇 | `-` |
| `  └ name` | body | string | 是 | 门店名称 | `测试门店4` |
| `  └ biz_type` | body | mixed | 是 | 业务类型 2:到店自提 | `2` |
| `  └ biz_line` | body | mixed | 否 | 行业线(燃油场景必填) 0:电动车 1:服饰 2:新车 3:燃油 | `3` |
| `  └ store_code` | body | string | 是 | 门店编码 | `A014` |
| `  └ open_time` | body | object | 是 | 营业时间 | `` |
| `    └ custom` | body | string | 否 | - | `-` |
| `    └ day_map` | body | string | 是 | 1:周一、2:周一、3:周三、4:周四、5:周五、6:周六、7:周日  时间是空格分隔，比如08:30-11:00 13:00-17:00 | `{ "1": "08:00-20:00", "2": "08:00-20:00", "3": "08:00-20:00", "4": "08:00-20:00", "5": "08:00-20:00", "6": "08:00-20:00", "7": "08:00-20:00" }` |
| `  └ city` | body | string | 是 | 市 | `上海市` |
| `  └ threshold` | body | mixed | 否 | 门店接单阈值 | `100` |
| `  └ province_code` | body | string | 否 | 省份code | `-` |
| `  └ street_code` | body | string | 否 | 4级地址code | `-` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/batchCreateStore?app_key=your_appkey_here&method=pickup.batchCreateStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 批量创建结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -301:Error 1105 (HY000): unexpected EOF（sub_code: isv.business-failed:-301） | 请稍后再试 |
| `50002` | 业务处理失败 / -32:提交门店信息异常, 请修改后重试（sub_code: isv.business-failed:-32） | 请修改门店信息后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "create_store_failed_res_list": [
        {
          "fail_reason": "-",
          "store_info": {
            "address": "-",
            "biz_type": "-",
            "city": "-",
            "city_code": "-",
            "contact": "-",
            "district": "-",
            "district_code": "-",
            "latitude": "-",
            "longitude": "-",
            "name": "-",
            "open_time": {
              "custom": "-",
              "day_map": {}
            },
            "province": "-",
            "province_code": "-",
            "rel_shop_id": "-",
            "store_code": "-",
            "street": "-",
            "street_code": "-"
          }
        }
      ],
      "fail_cnt": "0",
      "success_cnt": "1"
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
  "sub_code": "isv.business-failed:-301",
  "sub_msg": "-301:Error 1105 (HY000): unexpected EOF"
}
```

## 备注
