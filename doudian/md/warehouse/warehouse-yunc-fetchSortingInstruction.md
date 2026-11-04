# 获取分拣指令

> yunc.fetchSortingInstruction — 获取分拣指令

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取分拣指令 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-fetchSortingInstruction` |
| 接口 ID | `doudian.warehouse.yunc.fetchSortingInstruction` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/fetchSortingInstruction` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2669 |
| 更新日期 | `2022-11-08` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `scene_name` | body | string | 是 | 场景名称: 快递分拣:`express_sorting`; 详细枚举值请联系仓储团队获取 | `express_sorting` |
| `hu_ident_code` | body | string | 是 | 操作对象识别码, 如 面单号, 容器条码等 | `SF609790790` |
| `weight` | body | number | 否 | 重量(单位g) | `10` |
| `labor_id` | body | string | 是 | 劳动力ID, 对于设备来说是就是deviceId | `123456` |
| `extend` | body | string | 否 | 扩展信息 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/fetchSortingInstruction?app_key=your_appkey_here&method=yunc.fetchSortingInstruction&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sorting_instruction` | object | 分拣指令 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 无法识别的面单号（sub_code: isv.business-failed:3000） | 无法识别的面单号 |

## 响应示例

成功：

```json
{
  "data": {
    "sorting_instruction": {
      "extend": {},
      "sorting_grid_no": "A"
    }
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
  "sub_code": "isv.business-failed:3000",
  "sub_msg": "无法识别的面单号"
}
```

## 备注
