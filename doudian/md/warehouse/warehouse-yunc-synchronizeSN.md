# yunc.synchronizeSN

> WMS回传SN信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.yunc.synchronizeSN` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/synchronizeSN` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2174 |
| 更新日期 | `2022-07-14` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 字段长度(16):仓库编码 | `101` |
| `order_no` | body | string | 是 | 字段长度(64):单据号 | `IB7116738893613334828` |
| `order_type` | body | string | 是 | 字段长度(32):单据类型（CGRK=采购入库，XTRK=销退入库，DBRK=调拨入库，SCRK=生产入库，QTRK=其他入库，TCCK=退仓出库，XSCK=销售出库，DBCK=调拨出库，SCCK=生产出库，QTCK=其他出库，INVENTORY_TAKING_PROFIT=库存盘点-盘盈，INVENTORY_TAKING_LOSS=库存盘点-盘亏） | `CGRK` |
| `owner_code` | body | string | 是 | 字段长度(32):货主编码 | `BD10000029` |
| `track_no` | body | string | 否 | 字段长度(64):运单号 | `SF80989723471872` |
| `express_code` | body | string | 否 | 字段长度(32):快递公司编码（字节平台编码） | `shunfeng` |
| `occur_time` | body | number | 是 | 业务发生时间 | `1657523230` |
| `idempotent_no` | body | string | 是 | 字段长度(128):幂等号 | `UNIQ1657523230` |
| `extend` | body | string | 否 | 扩展信息 | `` |
| `sn_list` | body | array | 是 | SN码信息列表 | `` |
| `  └ sn_code` | body | string | 是 | 字段长度(128):SN码 | `SN001` |
| `  └ cargo_code` | body | string | 是 | 字段长度(64):货品编码 | `7088142226379292972` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/synchronizeSN?app_key=your_appkey_here&method=yunc.synchronizeSN&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 错误码 | `0` |
| `msg` | string | 错误信息 | `响应成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "响应成功"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
