# 批量获取视频信息

> material.mGetPlayInfo — 批量获取视频信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量获取视频信息 |
| 文档地址 | `/docs/doudian/material/material-material-mGetPlayInfo` |
| 接口 ID | `doudian.material.material.mGetPlayInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/mGetPlayInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/2164 |
| 更新日期 | `2022-11-09` |

## 接口说明

- 文档书: 素材中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vid_list` | body | array | 是 | vid列表，列表长度(1, 20) | `["asd123asdqw" ,"asd1wdsadas"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/mGetPlayInfo?app_key=your_appkey_here&method=material.mGetPlayInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_map` | string | 获取成功map，key为vid，value是视频的播放信息 | `` |
| `failed_map` | string | 获取失败map，key为vid | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:20001） | 检查参数是否符合要求 |
| `40004` | 非法的参数 / 审核中/审核不通过的视频不支持预览（sub_code: isv.parameter-invalid:20005） | 等素材审核通过之后再查询 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:10003） | 系统异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_map": {},
    "success_map": {}
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
  "sub_msg": "参数错误"
}
```

## 备注
