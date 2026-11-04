# 批量查询vid

> max.playinfo — 批量查询vid

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量查询vid |
| 文档地址 | `/docs/doudian/shop/shop-max-playinfo` |
| 接口 ID | `doudian.shop.max.playinfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/max/playinfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2832 |
| 更新日期 | `2025-09-18` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vids` | body | array | 是 | 视频云的 vid 列表 | `aaa,bbb` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/max/playinfo?app_key=your_appkey_here&method=max.playinfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status_code` | mixed | 状态码 | `0` |
| `status_msg` | string | 状态描述 | `success` |
| `data` | object | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 啊哦，服务器打瞌睡了，再试一次吧～（sub_code: isp.service-error:4） | 再次尝试 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 检查参数 |
| `50002` | 业务处理失败 / 用户未登陆（sub_code: isv.business-failed:8） | 请登陆 |
| `50002` | 业务处理失败 / 请升级客户端（sub_code: isv.business-failed:2146） | 升级客户端 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "fail_map": {},
      "success_map": {}
    },
    "status_code": "0",
    "status_msg": "success"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:4",
  "sub_msg": "啊哦，服务器打瞌睡了，再试一次吧～"
}
```

## 备注
