# 新增自动呼叫运力配置

> superm.setStoreAutoCallRider — 新增自动呼叫运力配置

| 元信息 | 值 |
| --- | --- |
| 中文名 | 新增自动呼叫运力配置 |
| 文档地址 | `/docs/doudian/logistics/logistics-superm-setStoreAutoCallRider` |
| 接口 ID | `doudian.logistics.superm.setStoreAutoCallRider` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/setStoreAutoCallRider` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2800 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 店铺的门店ID | `73837742` |
| `op_type` | body | string | 是 | 自动呼叫运力设置状态；open 开启 close  关闭 | `open` |
| `service_type` | body | number | 否 | 自动呼叫运力策略； 0：接单后立即呼叫  1：接单后延迟呼叫 | `1` |
| `delay_time` | body | number | 否 | 接单后延时呼叫时间，service_type为1时生效，单位分钟，范围[1,15] 延迟时间仅支持1-15分钟 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/orienPlanAuthors?app_key=your_appkey_here&method=buyin.orienPlanAuthors&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 店铺ID不能为空（sub_code: isv.missing-parameter:40011） | 请确认店铺ID参数格式正确 |
| `40002` | 缺少必选参数 / 门店ID不能为空（sub_code: isv.missing-parameter:40012） | 请确认门店ID参数格式正确 |
| `50002` | 业务处理失败 / 请输入正确的操作信息（sub_code: isv.business-failed:40100） | 请输入正确的操作信息 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20201） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20112） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:50114） | store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 未开通平台运力服务（sub_code: isv.business-failed:50111） | 未开通平台运力服务 |
| `50002` | 业务处理失败 / 请设置自动呼叫运力策略 1：接单后立即呼叫  2：接单后延迟呼叫（sub_code: isv.business-failed:40000） | 请设置自动呼叫运力策略 1：接单后立即呼叫  2：接单后延迟呼叫 |
| `50002` | 业务处理失败 / 120051:未开通平台运力服务（sub_code: isv.business-failed:120051） | 120051:未开通平台运力服务 |

## 响应示例

成功：

```json
{
  "data": {
    "orien_plan_authors": [
      {
        "apply_id": "1",
        "apply_info": "申请加入",
        "apply_suc_time": "1625480546",
        "apply_time": "1625480546",
        "audit_status": "1",
        "buyin_id": "11111",
        "end_time": "end_time",
        "orien_plan_id": "1233221",
        "user_name": "达人昵称"
      }
    ],
    "total": "100"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:40011",
  "sub_msg": "店铺ID不能为空"
}
```

## 备注
