# install.order.supplierUpdate

> 服务商修改预约信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.supplierUpdate` |
| 中文名 | 服务商修改预约信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/supplierUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5784 |
| 更新日期 | `2023-12-21` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 实操单号 | `""` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `""` |
| `appointment_time` | body | string | 否 | 预约时间，格式："yyyy-MM-dd HH:mm:ss~yyyy-MM-dd HH:mm:ss" | `""` |
| `operator_name` | body | string | 否 | 上门师傅名字 | `""` |
| `operator_mobile` | body | string | 否 | 上门师傅手机号，格式，真实号：主机号；虚拟号：主机号-分机号； | `""` |
| `operate_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityList?app_key=your_appkey_here&method=product.qualityList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000006:状态机跃迁校验错误（sub_code: isv.business-failed:10000006） | 10000006:状态机跃迁校验错误 |
| `50002` | 业务处理失败 / 10000000:请求参数错误（sub_code: isv.business-failed:10000000） | 10000000:请求参数错误 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

## 响应示例

成功：

```json
{
  "data": {
    "quality_list": [
      {
        "base_score": "20",
        "meet_standard": "2",
        "problem_num_to_improve": "2",
        "problem_type_distribution": [
          {
            "num": "1",
            "type_name": "关键信息需优化"
          }
        ],
        "product_id": "3502373827210525080",
        "product_name": "奈克牌皮鞋",
        "quality_score": {
          "level": "lv3",
          "score": "100",
          "version": "middle_score"
        }
      }
    ],
    "total": "50"
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
  "sub_code": "isv.business-failed:10000006",
  "sub_msg": "10000006:状态机跃迁校验错误"
}
```

## 备注
