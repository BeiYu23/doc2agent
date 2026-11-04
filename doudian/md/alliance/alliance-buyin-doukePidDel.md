# 独立抖客PID删除

> buyin.doukePidDel — 独立抖客PID删除

| 元信息 | 值 |
| --- | --- |
| 中文名 | 独立抖客PID删除 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-doukePidDel` |
| 接口 ID | `doudian.alliance.buyin.doukePidDel` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/doukePidDel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/3079 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `pids` | body | string | 是 | PID列表，多个用,分隔，最多200个 | `dy_234_5767, dy_234_57698` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/doukePidDel?app_key=your_appkey_here&method=buyin.doukePidDel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 参数校验失败 |
| `40004` | 非法的参数 / 需【独立抖客】角色授权后访问（sub_code: isv.parameter-invalid:8198） | 需【独立抖客】角色授权后访问 |

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
  "sub_code": "isv.business-failed:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
