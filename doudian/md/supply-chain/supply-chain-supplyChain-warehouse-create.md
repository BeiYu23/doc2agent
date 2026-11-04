# 创建区域仓

> supplyChain.warehouse.create — 创建区域仓

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建区域仓 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-warehouse-create` |
| 接口 ID | `doudian.supply-chain.supplyChain.warehouse.create` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/warehouse/create` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/2560 |
| 更新日期 | `2022-09-28` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 外部仓id | `w11111111` |
| `name` | body | string | 是 | 区域仓名称 | `测试仓` |
| `intro` | body | string | 是 | 区域仓信息描述 | `测试仓简介` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/warehouse/create?app_key=your_appkey_here&method=supplyChain.warehouse.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `warehouse_id` | string | 平台侧返回的仓编码与out_warehouse_id一一对应 | `w11111111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "warehouse_id": "w11111111"
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
