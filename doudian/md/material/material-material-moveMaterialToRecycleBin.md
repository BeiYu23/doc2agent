# 移动素材到回收站

> material.moveMaterialToRecycleBin — 移动素材到回收站

| 元信息 | 值 |
| --- | --- |
| 中文名 | 移动素材到回收站 |
| 文档地址 | `/docs/doudian/material/material-material-moveMaterialToRecycleBin` |
| 接口 ID | `doudian.material.material.moveMaterialToRecycleBin` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/moveMaterialToRecycleBin` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/951 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `material_ids` | body | array | 是 | 素材id列表，（1）数量不得超过100；（2）同一级目录下的素材 | `["7000291764753940780"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/moveMaterialToRecycleBin?app_key=your_appkey_here&method=material.moveMaterialToRecycleBin&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_ids` | array | 成功的素材id列表 | `["7000291764753940780"]` |
| `failed_map` | string | 失败素材列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 素材ID无效或状态错误（sub_code: isv.parameter-invalid:20001） | 素材不存在，原因有：已被删除或主从延迟导致素材不存在 |
| `40004` | 非法的参数 / 数据可能已被修改，请刷新后重新提交（sub_code: isv.parameter-invalid:22004） | 重新选择参数，再重试 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_ids": "[\"7000291764753940780\"]"
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
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "素材ID无效或状态错误"
}
```

## 备注
