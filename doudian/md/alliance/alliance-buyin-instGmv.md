# 【已下线，公告

> buyin.instGmv — 【已下线，公告https://op.jinritemai.com/docs/notice-docs/21/7407】
查询机构某天的选品GMV，不包括抖音应用选品GMV数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【已下线，公告 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-instGmv` |
| 接口 ID | `doudian.alliance.buyin.instGmv` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/instGmv` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1652 |
| 更新日期 | `2022-11-15` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `date` | body | string | 是 | 日期（只支持查询[t-60,t-2]的GMV） | `2022-02-01` |
| `search_type` | body | number | 否 | 查询粒度（1-查询当前应用，2-查询应用所属工具服务商，不包括抖音应用选品GMV数据） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
