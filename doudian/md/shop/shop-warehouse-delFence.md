# 删除电子围栏

> warehouse.delFence — 删除电子围栏

| 元信息 | 值 |
| --- | --- |
| 中文名 | 删除电子围栏 |
| 文档地址 | `/docs/doudian/shop/shop-warehouse-delFence` |
| 接口 ID | `doudian.shop.warehouse.delFence` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/delFence` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2065 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `fence_id` | body | mixed | 否 | 内部围栏id(和外部2选1，如果传了，则优先使用这个) | `4922530157611679612` |
| `out_fence_id` | body | string | 否 | 外部围栏id | `fence02` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/delFence?app_key=your_appkey_here&method=warehouse.delFence&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 围栏id不存在（sub_code: isv.parameter-invalid:2） | 修改参数 |
| `20000` | 系统错误 / 删除围栏失败（sub_code: isp.service-error:9999） | 重试 |
| `50002` | 业务处理失败 / 请检查传入参数（sub_code: isv.business-failed:2122） | 修改传入参数 |
| `50002` | 业务处理失败 / 检查围栏是否已经绑定（sub_code: isv.business-failed:2121006） | 删除围栏前先解绑 |
| `20000` | 系统错误 / 操作失败，请重试（sub_code: isp.service-error:2129999） | 重试 |
| `50002` | 业务处理失败 / 服务器打瞌睡了，请稍后再试。（sub_code: isv.business-failed:6001001） | 重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2",
  "sub_msg": "围栏id不存在"
}
```

## 备注
