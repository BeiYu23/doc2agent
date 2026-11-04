# trace.cancelShop

> 订单链路监控删除用户

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.order.trace.cancelShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trace/cancelShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/15/2793 |
| 更新日期 | `2022-12-13` |

## 接口说明

- 文档书: 订单API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/trace/cancelShop?app_key=your_appkey_here&method=trace.cancelShop&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_name` | string | 店铺名称 | `测试店铺名称` |
| `status` | string | 用户开通状态。已关闭，授权已过期 | `已关闭` |
| `create_at` | string | 开通时间；格式：yyyy-MM-dd HH:mm:ss | `2022-11-30 10:52:53` |
| `update_at` | string | 最后更新时间，此次为关闭时间；格式：yyyy-MM-dd HH:mm:ss | `2022-11-30 10:52:53` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 当前用户未开通订单轨迹服务（sub_code: isv.parameter-invalid:605090004） | 用户未开通，无需调用删除 |
| `20000` | 系统错误 / 内部服务异常，请稍后重试（sub_code: isp.service-error:605090001） | 内部服务异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "create_at": "2022-11-30 10:52:53",
    "shop_name": "测试店铺名称",
    "status": "已关闭",
    "update_at": "2022-11-30 10:52:53"
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
  "sub_code": "isv.parameter-invalid:605090004",
  "sub_msg": "当前用户未开通订单轨迹服务"
}
```

## 备注
