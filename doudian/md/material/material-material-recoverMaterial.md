# 从回收站中恢复素材

> material.recoverMaterial — 从回收站中恢复素材

| 元信息 | 值 |
| --- | --- |
| 中文名 | 从回收站中恢复素材 |
| 文档地址 | `/docs/doudian/material/material-material-recoverMaterial` |
| 接口 ID | `doudian.material.material.recoverMaterial` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/recoverMaterial` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/954 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_ids` | body | array | 是 | 素材id列表 | `["7000291764753940780"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/recoverMaterial?app_key=your_appkey_here&method=material.recoverMaterial&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_ids` | array | 成功操作的素材id列表 | `[7000291764753940780]` |
| `failed_map` | string | 失败素材列表及失败原因 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 20001:素材ID无效，请输入正确的素材ID（sub_code: isv.business-failed:20001） | 20001:素材ID无效，请输入正确的素材ID |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_ids": "[7000291764753940780]"
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
  "sub_code": "isv.business-failed:20001",
  "sub_msg": "20001:素材ID无效，请输入正确的素材ID"
}
```

## 备注
