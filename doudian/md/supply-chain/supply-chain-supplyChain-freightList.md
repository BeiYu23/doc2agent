# 获取供应商运费列表

> supplyChain.freightList — 获取供应商运费列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取供应商运费列表 |
| 文档地址 | `/docs/doudian/supply-chain/supply-chain-supplyChain-freightList` |
| 接口 ID | `doudian.supply-chain.supplyChain.freightList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/freightList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/7430 |
| 更新日期 | `2025-04-28` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/freightList?app_key=your_appkey_here&method=supplyChain.freightList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 0代表正确 | `响应码` |
| `msg` | string | 错误信息 | `错误信息` |
| `data` | object | 运费数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "响应码",
    "data": {
      "list": [
        {
          "id": "运费id",
          "name": "运费名称"
        }
      ],
      "total": "数量"
    },
    "msg": "错误信息"
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
