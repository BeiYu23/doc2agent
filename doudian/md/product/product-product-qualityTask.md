# product.qualityTask

> 商品每日诊断任务查询API

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.qualityTask` |
| 中文名 | 商品每日诊断任务查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/qualityTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1829 |
| 更新日期 | `2021-09-08` |

## 接口说明

- 文档书: 商品API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `brief_only` | body | boolean | 否 | 是否只返回简要信息，不写默认false | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityTask?app_key=your_appkey_here&method=product.qualityTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_num_total` | number | 总共需要诊断的商品数 | `10` |
| `product_num_finished` | number | 已经诊断过的商品数 | `10` |
| `task_status` | number | 任务状态，0-初始化，1-进行中，2-已完成 | `2` |
| `product_num_to_improve_total` | number | 待优化商品数，仅brief_only为false返回 | `10` |
| `problem_num_total` | number | 可优化项总数，仅brief_only为false返回 | `10` |
| `problem_num_to_improve` | number | 待优化项数量，仅brief_only为false返回 | `10` |
| `task_finish_time` | string | 任务完成时间，仅brief_only为false返回 | `2021-09-07 01:21:46` |
| `problem_type_distribution` | array | 问题类型分布，仅brief_only为false返回 | `` |
| `task_id` | number | 任务ID | `15293` |
| `standard_rate` | string | 达标率，百分比 | `10` |
| `is_standard` | boolean | 是否达标 | `true` |
| `meet_standard_num` | number | 达标商品数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:2030001） | 等待后重试 |
| `50002` | 业务处理失败 / 处理超时（sub_code: isv.business-failed:2030002） | 等待后重试 |
| `40002` | 缺少必选参数 / 缺少必要参数（sub_code: isv.missing-parameter:2030003） | 补充必要参数 |
| `40004` | 非法的参数 / 参数值非法（sub_code: isv.parameter-invalid:2030004） | 按要求填写参数值 |
| `20000` | 系统错误 / 读取数据失败（sub_code: isp.service-error:2030201） | 等待后重试 |
| `50002` | 业务处理失败 / 2030013:读取任务失败（sub_code: isv.business-failed:2030013） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "is_standard": "true",
    "meet_standard_num": "1",
    "problem_num_to_improve": "10",
    "problem_num_total": "10",
    "problem_type_distribution": [
      {
        "num": "2",
        "type_key": "1",
        "type_name": "商品信息不规范"
      }
    ],
    "product_num_finished": "10",
    "product_num_to_improve_total": "10",
    "product_num_total": "10",
    "standard_rate": "10",
    "task_finish_time": "2021-09-07 01:21:46",
    "task_id": "15293",
    "task_status": "2"
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
  "sub_code": "isp.service-error:2030001",
  "sub_msg": "系统异常"
}
```

## 备注
