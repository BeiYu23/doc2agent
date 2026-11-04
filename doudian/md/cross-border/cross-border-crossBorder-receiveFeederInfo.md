# crossBorder.receiveFeederInfo

> 分拨直送服务商回传支线单据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossBorder.receiveFeederInfo` |
| 中文名 | 分拨直送服务商回传支线单据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/receiveFeederInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/4140 |
| 更新日期 | `2023-06-27` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operator` | body | string | 是 | 操作人(账号) | `xiaoming` |
| `data` | body | object | 是 | 分拨直送数据 | `` |
| `  └ bagging_num` | body | string | 否 | 集包号 | `HB23060900002` |
| `  └ event_type` | body | number | 是 | 事件类型（EventType），1:节点扭转事件 2:异常上报事件 | `1` |
| `  └ event_code` | body | string | 是 | 事件code（EventCode） | `2001` |
| `  └ event_msg` | body | string | 是 | 事件msg（EventMsg) | `包裹异常信息` |
| `  └ occurrence_time` | body | number | 是 | 毫秒时间戳 | `1686659544000` |
| `  └ waybill_no` | body | string | 是 | 运单号 | `SF1380030202991` |
| `  └ pics` | body | array | 否 | 图片url列表 最多5张 | `图片url列表` |
| `vendor` | body | string | 是 | 字节给供应链服务商定义的编码 | `ZZJC` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/receiveFeederInfo?app_key=your_appkey_here&method=crossBorder.receiveFeederInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 0 表示成功 | `0` |
| `msg` | string | msg信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1002） | 检查参数 |
| `40004` | 非法的参数 / 单据非法（sub_code: isv.parameter-invalid:1003） | 检查运单号是否正确 |
| `50002` | 业务处理失败 / 节点时序状态有误（sub_code: isv.business-failed:1004） | 检查事件是否有时序问题 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:1005） | 可以联系运营，进行oncall 技术 |
| `40004` | 非法的参数 / 记录不存在（sub_code: isv.parameter-invalid:1006） | 记录不存在 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
  "sub_code": "isv.parameter-invalid:1002",
  "sub_msg": "参数错误"
}
```

## 备注
