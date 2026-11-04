# 直播间分销物料查询

> buyin.liveShareMaterial — 直播间分销物料查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 直播间分销物料查询 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-liveShareMaterial` |
| 接口 ID | `doudian.alliance.buyin.liveShareMaterial` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/liveShareMaterial` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1396 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `author_type` | body | mixed | 否 | 1 品牌 2 达人(默认值) | `1` |
| `author_levels` | body | array | 否 | 作者电商等级，0-7级 | `1` |
| `frist_cids` | body | array | 否 | 商品行业类目，列表类型；使用【/alliance/activityProductCategoryList】接口获取 | `23` |
| `author_info` | body | string | 否 | 达人昵称或者账号 | `我的昵称` |
| `page` | body | mixed | 是 | 分页，1开始 | `1` |
| `page_size` | body | mixed | 是 | 分页大小 | `10` |
| `sort_by` | body | mixed | 否 | 排序字段: 1-综合；2-销量；3-佣金率；4-粉丝数 | `1` |
| `sort_type` | body | mixed | 否 | 排序方式：0-降序；1-升序 | `0` |
| `live_status` | body | mixed | 否 | 开关播状态：0:所有，1:开播，2:关播 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/liveShareMaterial?app_key=your_appkey_here&method=buyin.liveShareMaterial&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `20` |
| `data` | array | 列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 无效分页大小（sub_code: isv.parameter-invalid:4097） | 无效分页大小 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 需【抖客】角色授权后访问（sub_code: isv.business-failed:4198） | 需【抖客】角色授权后访问 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "author_level": "1",
        "author_name": "我是kol",
        "author_openid": "fdfwe",
        "author_pic": "http://fake.png",
        "average_commission_rate": "30",
        "average_gmv": "1111111",
        "buyin_id": "6523908954358943",
        "city": "广州",
        "fans_num": "222",
        "gender": "male",
        "has_redpack": "false",
        "is_ecom": "true",
        "is_live": "true",
        "live_preview_auth": "false",
        "product_category": "测试类目",
        "province": "广东",
        "room_id": "1234567890"
      }
    ],
    "total": "20"
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
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
