# material.get_cap_info

> 获取商家容量详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.get_cap_info` |
| 中文名 | 获取商家容量 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/get_cap_info` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1694 |
| 更新日期 | `2022-11-17` |

## 接口说明

- 文档书: 素材中心API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/get_cap_info?app_key=your_appkey_here&method=material.get_cap_info&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total_capacity` | number | 总容量，单位KB | `188743680` |
| `total_capacity_used` | number | 已使用容量，单位KB | `681717` |
| `photo_capacity` | number | 图片总容量，单位KB | `83886080` |
| `photo_capacity_used` | number | 图片已使用容量，单位KB | `74280` |
| `video_capacity` | number | 视频总容量，单位KB | `104857600` |
| `video_capacity_used` | number | 视频已使用容量，单位KB | `607437` |
| `equity_info` | array | 当前生效的权益列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 店铺ID错误，请输入正确的店铺ID（sub_code: isv.missing-parameter:20001） | 补充ShopId |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 稍后重试 |
| `40004` | 非法的参数 / 素材中心已失效，请联系客服处理（sub_code: isv.parameter-invalid:30004） | 联系客服 |

## 响应示例

成功：

```json
{
  "data": {
    "equity_info": [
      {
        "begin_time": "1641034518",
        "end_time": "1672570518",
        "equity_type": "B",
        "equity_type_desc": "B类商家权益",
        "photo_capacity": "20971520",
        "total_capacity": "41943040",
        "video_capacity": "20971520"
      }
    ],
    "photo_capacity": "83886080",
    "photo_capacity_used": "74280",
    "total_capacity": "188743680",
    "total_capacity_used": "681717",
    "video_capacity": "104857600",
    "video_capacity_used": "607437"
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
  "sub_code": "isv.missing-parameter:20001",
  "sub_msg": "店铺ID错误，请输入正确的店铺ID"
}
```

## 备注
