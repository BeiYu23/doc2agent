# topup.microAppCreateOrder

> 运营商小程序下单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.topup.microAppCreateOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/microAppCreateOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7705 |
| 更新日期 | `2025-08-18` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `token` | body | string | 是 | 下单token | `202505190833318155DAF78404669DBAC7` |
| `phone_number` | body | string | 是 | 手机号 | `13012345678` |
| `amount` | body | mixed | 是 | 充值面额，单位分 | `5000` |
| `price` | body | mixed | 是 | 优惠后价格，单位分 | `5000` |
| `seller_order_no` | body | string | 否 | 移动侧订单号 | `123456` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/microAppCreateOrder?app_key=your_appkey_here&method=topup.microAppCreateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `url` | string | 下单schema | `sslocal://microapp?app_id=ttcfe7b95a50e94b4901&bdp_log=%7B%22enter_from_merge%22%3A%22recharge_center%22%2C%22enter_position%22%3A%22china_mobile%22%2C%22entrance_form%22%3A%22recharge%22%2C%22launch_from%22%3A%22recharge_center%22%7D&launch_config=%7B%22xscreen_config%22%3A%7B%22rate%22%3A0.7%7D%7D&launch_mode=hostStack&scene=0&start_page=pages%2Findex%2Fcharge%3Famount%3D5100%26env%3Dppe_topup_jiyun%26order_token%3D20250818143943490F6A0CFC0C774E8FCE%26phone_number%3D18301360128%26price%3D5000%26shop_id%3D63141224&uniq_id=S202508181439434821957331557731942400b6dd50568b87&version=v2&version_type=latest&bdpsum=567c3aa` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 当前页面停留时间过长，请返回上级页面后重试（sub_code: isv.business-failed:1） | 当前页面停留时间过长，请返回上级页面后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "url": "sslocal://microapp?app_id=ttcfe7b95a50e94b4901&bdp_log=%7B%22enter_from_merge%22%3A%22recharge_center%22%2C%22enter_position%22%3A%22china_mobile%22%2C%22entrance_form%22%3A%22recharge%22%2C%22launch_from%22%3A%22recharge_center%22%7D&launch_config=%7B%22xscreen_config%22%3A%7B%22rate%22%3A0.7%7D%7D&launch_mode=hostStack&scene=0&start_page=pages%2Findex%2Fcharge%3Famount%3D5100%26env%3Dppe_topup_jiyun%26order_token%3D20250818143943490F6A0CFC0C774E8FCE%26phone_number%3D18301360128%26price%3D5000%26shop_id%3D63141224&uniq_id=S202508181439434821957331557731942400b6dd50568b87&version=v2&version_type=latest&bdpsum=567c3aa"
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
  "sub_code": "isv.business-failed:1",
  "sub_msg": "当前页面停留时间过长，请返回上级页面后重试"
}
```

## 备注
