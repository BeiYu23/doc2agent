# logistics.ind.aoi.push

> 门店入驻后，自动/手动向承运商同步门店信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.ind.aoi.push` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/ind/aoi/push` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2455 |
| 更新日期 | `2022-11-02` |

## 接口说明

- 文档书: 物流发货API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_code` | body | string | 是 | 门店编码，由字节在门店创建/更新时同步给抖音平台 | `123456` |
| `instant_delivery_code` | body | string | 是 | 外部运力公司业务身份 | `外部公司入驻时的code码` |
| `aoi_id` | body | string | 是 | 电子围栏的id,运力公司保障一个电子围栏id唯一性 | `123456` |
| `aoi_type` | body | string | 是 | 回传的电子围栏是标准圆形还是多边形 | `circle,polygon` |
| `aoi_area_circle` | body | array | 否 | 若aoi_type=circle，必填 单位: m 圆心+半径 | `` |
| `  └ location` | body | object | 否 | 圆心经纬度 | `` |
| `    └ longitude` | body | string | 是 | 经度 | `111.23` |
| `    └ latitude` | body | string | 是 | 维度 | `111.23` |
| `    └ standard` | body | string | 是 | 地图标准 | `GaoDe` |
| `  └ circle_radius` | body | number | 是 | 半径 | `10000` |
| `aoi_area_polygon_list` | body | string | 否 | 若aoi_category=polygon，则回传经纬度点集合 构成的电子围栏多边形的经纬度坐标(高德体系经纬度) 例如: {   经度A,纬度A;    经度B,纬度B;   经度C,纬度C; } | `{{   经度A,纬度A;    经度B,纬度B;   经度C,纬度C; }}` |
| `aoi_op_type` | body | string | 是 | 变更类型 | `{aoi_type=1,新增门店可达电子围栏} {aoi_type=2,修改门店可达电子围栏} {aoi_type=3,启用门店可达电子围栏} {aoi_type=4,停用门店可达电子围栏}` |
| `fulfill_service` | body | array | 否 | 门店到此电子围栏的服务 | `无接触派送` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.ind.aoi.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `return_code` | string | 错误码，0 - 成功 | `0` |
| `message` | string | 错误信息，失败时填写 | `xx错了` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "message": "xx错了",
    "return_code": "0"
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
