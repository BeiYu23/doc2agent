# pickup.batchBindStoreLibrary

> 门店组批量绑定门店

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.store.pickup.batchBindStoreLibrary` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pickup/batchBindStoreLibrary` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1559/7237 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 自提门店API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `library_id` | body | string | 是 | 门店组id | `7459680072136671532` |
| `store_infos` | body | array | 是 | 门店id列表 | `` |
| `  └ store_id` | body | string | 是 | 门店ID | `1138991967` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pickup/batchBindStoreLibrary?app_key=your_appkey_here&method=pickup.batchBindStoreLibrary&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_count` | mixed | 成功数量 | `1` |
| `fail_count` | mixed | 失败数量 | `0` |
| `failed_file` | string | 失败的文件链接 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -3:门店库id不存在（sub_code: isv.business-failed:-3） | 请修改门店库 |
| `50002` | 业务处理失败 / -1:RPCError{PSM:[cmp.ecom.vshop] Method:[GetStoreLibraryInfo] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS\|ecom.logistics.resource_management:default:lq:\|cmp.ecom.vshop:default:lq::\|GetStoreLibraryInfo\|prod\| onOverQPSLimit, comment=cluster_limits_749185, threshold=2, unit=SECOND, instance=fdbd:dc03:11:621::44,fed-dp-4f78682c8f-5c4f957ddd-gj4t7] BizStatusCode:[0] BizStatusMessage:[]}（sub_code: isv.business-failed:-1） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_count": "0",
    "failed_file": "-",
    "success_count": "1"
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
  "sub_msg": "-3:门店库id不存在"
}
```

## 备注
