# 达人抖客红包

> buyin.distributionRedpackDetailList — 达人抖客红包详情

| 元信息 | 值 |
| --- | --- |
| 中文名 | 达人抖客红包 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-distributionRedpackDetailList` |
| 接口 ID | `doudian.alliance.buyin.distributionRedpackDetailList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/distributionRedpackDetailList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2546 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `buyin_id` | body | string | 是 | 查询达人的百应ID | `1234567` |
| `page` | body | mixed | 否 | 起始值为1，不传默认值为1 | `1` |
| `page_size` | body | mixed | 否 | 最大值20，不传默认值为10 | `10` |
| `redpack_name` | body | string | 否 | 红包名称 | `红包` |
| `start_date` | body | string | 否 | 投放开始日期，格式2006-01-02 | `2006-01-02` |
| `end_date` | body | string | 否 | 投放结束日期，格式2006-01-02 | `2006-01-02` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/distributionRedpackDetailList?app_key=your_appkey_here&method=buyin.distributionRedpackDetailList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `redpack_list` | array | 红包信息 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 当前抖客未开通直播间分销业务权限（sub_code: isv.parameter-invalid:4113） | 当前抖客未开通直播间分销业务权限 |
| `40004` | 非法的参数 / 参数校验失败: 无效分页大小（sub_code: isv.parameter-invalid:4127） | 参数校验失败: 无效分页大小 |
| `40004` | 非法的参数 / 参数校验失败：达人百应id无效（sub_code: isv.parameter-invalid:4296） | 参数校验失败：达人百应id无效 |
| `40004` | 非法的参数 / 参数校验失败：日期无效（sub_code: isv.parameter-invalid:4297） | 参数校验失败：日期无效 |
| `40004` | 非法的参数 / 红包参数校验失败（sub_code: isv.parameter-invalid:4298） | 红包参数校验失败 |

## 响应示例

成功：

```json
{
  "data": {
    "redpack_list": [
      {
        "credit_type": "1:固定面额 2:随机面额",
        "end_apply_time": "2022-09-27 00:00:00",
        "left_amount": "1000",
        "left_num": "10",
        "name": "红包",
        "redpack_id": "123456789",
        "start_apply_time": "2022-09-27 00:00:00",
        "status": "1",
        "use_end_time": "2022-09-27 00:00:00",
        "use_start_time": "2022-09-27 00:00:00"
      }
    ],
    "total": "10"
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
  "sub_code": "isv.parameter-invalid:4097",
  "sub_msg": "参数校验失败"
}
```

## 备注
