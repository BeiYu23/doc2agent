# install.store.providerStoreAPIModifyStatus

> 到店安装门店状态修改

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.providerStoreAPIModifyStatus` |
| 中文名 | 到店安装门店状态修改 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerStoreAPIModifyStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7679 |
| 更新日期 | `2026-06-02` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 否 | 门店id列表 | `123` |
| `is_enable` | body | boolean | 否 | true:上线, false:下线 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerStoreAPIModifyStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -118:门店状态错误，当前状态不可被操作（sub_code: isv.business-failed:-118） | 清确认门店状态是否正确 |
| `50002` | 业务处理失败 / -102:获取服务商门店列表失败（sub_code: isv.business-failed:-102） | 请稍后再试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-118",
  "sub_msg": "-118:门店状态错误，当前状态不可被操作"
}
```

## 备注
