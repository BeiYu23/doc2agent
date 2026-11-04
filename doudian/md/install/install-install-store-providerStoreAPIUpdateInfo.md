# install.store.providerStoreAPIUpdateInfo

> 服务商门店更新API

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.providerStoreAPIUpdateInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerStoreAPIUpdateInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7680 |
| 更新日期 | `2026-06-02` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `open_time_desc` | body | array | 否 | 营业时间的描述（使用这个来解析出来营业时间） | `["周一至周五 10:00-20:00", "周六至周日 10:00-23:00"]` |
| `store_id` | body | mixed | 否 | 操作更新的门店ID YOUR_SECRET_KEY.go | `123` |
| `province` | body | string | 否 | 省 | `北京市` |
| `business_license_url` | body | string | 否 | 营业执照 | `https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/bf9ea417-4352-443a-94c1-565ca986df8c.jpeg` |
| `backup_contact_mobile` | body | string | 否 | 备用联系方式 | `18600000000` |
| `name` | body | string | 否 | 以下是可编辑字段 门店名称 | `测试门店` |
| `district` | body | string | 否 | 区 | `海淀区` |
| `contact` | body | string | 否 | 联系方式 | `18600000000` |
| `door_photo_url` | body | string | 否 | 门头照 | `https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/bf9ea417-4352-443a-94c1-565ca986df8c.jpeg` |
| `room_photo_url` | body | array | 否 | 店内照 可以多张 | `["https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/bf9ea417-4352-443a-94c1-565ca986df8c.jpeg"]` |
| `contact_name` | body | string | 否 | 联系人 | `刘先生` |
| `business_license_address` | body | string | 否 | 营业执照上的门店地址信息 | `https://lf-resource-tos.ecombdstatic.com/obj/ecom-logistics-resource/store_install/bf9ea417-4352-443a-94c1-565ca986df8c.jpeg` |
| `city` | body | string | 否 | 市 | `北京市` |
| `street` | body | string | 否 | 4级地址 街道/镇 | `花园路街道` |
| `store_code` | body | string | 否 | 更新门店自用编码 | `自用编码123` |
| `address` | body | string | 否 | 详细地址 | `中兴大厦` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerStoreAPIUpdateInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
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
