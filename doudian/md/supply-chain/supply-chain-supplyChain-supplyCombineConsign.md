# supplyChain.supplyCombineConsign

> 供货单合单发货

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyCombineConsign` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/supplyCombineConsign` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7903 |
| 更新日期 | `2025-11-28` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `combine_order_no` | body | string | 是 | 合单号 | `HD7577367719507400000` |
| `tms_code` | body | string | 是 | 快递商公司编码，如yunda | `yunda` |
| `tracking_no` | body | string | 是 | 快递单号 | `SF53798222352` |
| `package_list` | body | array | 是 | 供货单发货列表 | `` |
| `  └ ship_cnt` | body | mixed | 是 | 发货数量 | `1` |
| `  └ order_no` | body | string | 是 | 供货单号 | `CT7577367719507000000` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/supplyCombineConsign?app_key=your_appkey_here&method=supplyChain.supplyCombineConsign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | success | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数请求（sub_code: isv.parameter-invalid:1020） | 请参考错误信息，或联系对接人员 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:1000） | 请稍后再试，或联系对接人员 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2000） | 请参考错误信息，或联系对接人员 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "0"
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
  "sub_code": "isv.parameter-invalid:1020",
  "sub_msg": "非法参数请求"
}
```

## 备注
