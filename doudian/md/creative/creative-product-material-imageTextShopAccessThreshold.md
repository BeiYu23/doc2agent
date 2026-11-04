# open侧图文创意店铺准入校验

> product.material.imageTextShopAccessThreshold — open侧图文创意店铺准入校验

| 元信息 | 值 |
| --- | --- |
| 中文名 | open侧图文创意店铺准入校验 |
| 文档地址 | `/docs/doudian/creative/creative-product-material-imageTextShopAccessThreshold` |
| 接口 ID | `doudian.creative.product.material.imageTextShopAccessThreshold` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4254 |
| 更新日期 | `2023-08-03` |

## 接口说明

- 文档书: 创意管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=product.material.imageTextShopAccessThreshold&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `have_threshold` | boolean | 整体校验是否有权限，false-无权限，true-有权限 | `false` |
| `threshold_detail_info` | string | 具体几项校验结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 系统处理失败（sub_code: isv.business-failed:2012001） | 重试或者联系 |

## 响应示例

成功：

```json
{
  "data": {
    "have_threshold": "false",
    "threshold_detail_info": {}
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
  "sub_code": "isv.business-failed:2012001",
  "sub_msg": "系统处理失败"
}
```

## 备注
