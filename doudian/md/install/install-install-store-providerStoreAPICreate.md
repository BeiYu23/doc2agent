# install.store.providerStoreAPICreate

> 行业服务到店安装门店创建API

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.providerStoreAPICreate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerStoreAPICreate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7681 |
| 更新日期 | `2026-06-02` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_info` | body | object | 是 | 门店结构体 | `` |
| `  └ district` | body | string | 否 | 区/县 | `海淀区` |
| `  └ open_time_desc` | body | array | 否 | 字符串数组，写为如下格式： 周一至周五 10:00-17:00 周六至周日 10:00-17:00 周一至周五 和 周六至周日 是固定枚举，时间段写一个，要符合hh:mm的格式，周一至周五与营业时间之间是个空格分隔。营业开始时间和结束时间使用-符号分隔 | `["周一至周五 10:00-18:00", "周六至周日 10:00-22:00"]` |
| `  └ address` | body | string | 否 | 详细地址信息 | `中兴大厦` |
| `  └ business_license_url` | body | string | 否 | 营业执照的链接url | `https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/b07d37c8-3c30-45a3-a353-d9be31d9b3b5.jpeg` |
| `  └ door_image_url` | body | string | 否 | 门头照链接 | `https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/b07d37c8-3c30-45a3-a353-d9be31d9b3b5.jpeg` |
| `  └ contactor` | body | string | 否 | 联系方式(全数字字符串，不要出现-字符) | `18600000000` |
| `  └ back_up_contactor` | body | string | 否 | 备用手机号 | `18600000000` |
| `  └ contactor_name` | body | string | 否 | 联系人名字 | `刘先生` |
| `  └ store_name` | body | string | 是 | 门店名称 | `门店名称` |
| `  └ street` | body | string | 否 | 街道 | `花园路街道` |
| `  └ business_license_address` | body | string | 否 | 营业执照上的地址 | `北京市海淀区花园路街道中兴大厦` |
| `  └ province` | body | string | 否 | 省 | `北京市` |
| `  └ room_image_url` | body | array | 否 | 店内照片 | `["https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/b07d37c8-3c30-45a3-a353-d9be31d9b3b5.jpeg"]` |
| `  └ city` | body | string | 否 | 市 | `北京市` |
| `  └ store_code` | body | string | 否 | 门店编码 | `自用编码123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerStoreAPICreate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_id` | mixed | 返回的门店id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "store_id": "123"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
