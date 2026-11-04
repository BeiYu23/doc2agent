# supplyChain.supplyProduct.setOnline

> 上架产品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProduct.setOnline` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2558 |
| 更新日期 | `2022-09-28` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 是 | 产品id | `355653216545615442145` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/updatePostAmount?app_key=your_appkey_here&method=order.updatePostAmount&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 3207:编辑分销品错误\|RPCError{PSM:[ecom.bscp.gongxiao_manage] Method:[ProductOnShelf] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[1000] BizStatusMessage:[分销品上架治理审核中，暂不支持上架操作]}（sub_code: isv.business-failed:3207） | 3207:编辑分销品错误\|RPCError{PSM:[ecom.bscp.gongxiao_manage] Method:[ProductOnShelf] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[1000] BizStatusMessage:[分销品上架治理审核中，暂不支持上架操作]} |

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
  "sub_code": "isv.business-failed:3207",
  "sub_msg": "3207:编辑分销品错误|RPCError{PSM:[ecom.bscp.gongxiao_manage] Method:[ProductOnShelf] ErrType:[RPC_STATUS_CODE_NOT_ZERO] OriginalErr:[<nil>] BizStatusCode:[1000] BizStatusMessage:[分销品上架治理审核中，暂不支持上架操作]}"
}
```

## 备注
