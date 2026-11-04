# sms.getLabelList

> 获取标签列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.sms.getLabelList` |
| 中文名 | 获取标签列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/getLabelList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/6683 |
| 更新日期 | `2024-08-01` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/getLabelList?app_key=your_appkey_here&method=sms.getLabelList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tab_list` | array | 标签tab列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `80000` | 风控拦截 / 系统不可用拦截（sub_code: isv.risk-control-failed:628004410） | 待系统恢复 |

## 响应示例

成功：

```json
{
  "data": {
    "tab_list": [
      {
        "label_list": [
          {
            "disable": "false",
            "front_type": "7",
            "label_desc": "在平台上购买所选类目商品较多的人群",
            "label_id": "36",
            "label_name": "类目核心人群",
            "label_type": "7",
            "param_list": [
              {
                "param_desc": "\"\"",
                "param_id": "2",
                "param_name": "玩具乐器",
                "sub_param_list": [
                  {
                    "param_desc": "\"\"",
                    "param_id": "20019",
                    "param_name": "模玩/动漫/周边/娃圈/三坑/桌游"
                  }
                ]
              }
            ]
          }
        ],
        "sub_tab": [
          {
            "label_list": [
              {
                "disable": "true",
                "label_desc": "根据用户在抖音行为数据预测得出",
                "label_id": "1",
                "label_name": "八大人群",
                "label_type": "2",
                "param_list": [
                  {
                    "param_desc": "\"\"",
                    "param_id": "1",
                    "param_name": "小镇青年",
                    "sub_param_list": [
                      {
                        "param_id": "1",
                        "param_name": "甘肃省"
                      }
                    ]
                  }
                ]
              }
            ],
            "tab_name": "基础属性"
          }
        ],
        "tab_name": "基础标签"
      }
    ]
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
  "code": 80000,
  "msg": "风控拦截",
  "sub_code": "isv.risk-control-failed:628004410",
  "sub_msg": "系统不可用拦截"
}
```

## 备注
