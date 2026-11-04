# supplyChain.supplyProductV2.getQualificationConfig

> 获取类目下需要填写的资质列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.getQualificationConfig` |
| 中文名 | 获取类目下需要填写的资质列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6670 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 类目ID(叶子类目) | `20215` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `config_list` | array | 返回数据列表 | `` |
| `code` | mixed | 返回码 | `1000` |
| `msg` | string | 返回信息 | `“”` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductQualificationConfig] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS\|ecom.bscp.scm_open:default:hl:\|cmp.ecom.product_backend:de（sub_code: isv.business-failed:2000） | 2000:业务处理异常\|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductQualificationConfig] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS\|ecom.bscp.scm_open:default:hl:\|cmp.ecom.product_backend:de |

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
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "2000:业务处理异常|RPCError{PSM:[cmp.ecom.product_backend] Method:[GetProductQualificationConfig] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1604 cds_key=THRIFT_INGRESS|ecom.bscp.scm_open:default:hl:|cmp.ecom.product_backend:de"
}
```

## 备注
