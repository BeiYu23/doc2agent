# buyin.doukeCommandParseAndShare

> 口令解析&转链

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.doukeCommandParseAndShare` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/doukeCommandParseAndShare` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/4010 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `command` | body | string | 是 | 抖口令或短链 | `3.:/ hO长[抱拳]按????墆此条消息，搭[呲牙]揩ƿȎƲ[拥抱]ȳɫǹ搜索，查看商品详情ηηcuTRuYrzTv8Я\t##cuTRuYrzTv8##` |
| `share_params` | body | object | 否 | 转链参数，无需转链可不传 | `` |
| `  └ pid` | body | string | 否 | 抖客PID | `dy_123_233_2222` |
| `  └ external_info` | body | string | 否 | 自定义字段，只允许 数字、字母和_，限制长度为40 | `111_222` |
| `  └ need_share_info_field` | body | object | 否 | 所需的转链分享物料，默认仅返回deeplink（建议按需获取，获取多种会导致响应耗时增加） | `` |
| `    └ need_share_command` | body | boolean | 否 | 是否需要口令 | `false` |
| `    └ need_qrcode` | body | boolean | 否 | 是否需要二维码 | `false` |
| `    └ need_zlink` | body | boolean | 否 | 是否需要zlink | `false` |
| `    └ need_share_link` | body | boolean | 否 | 是否需要站外H5链接（仅商品生效） | `false` |
| `  └ platform` | body | mixed | 否 | 回流端标识 0：抖音 1：抖音极速版 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/doukeCommandParseAndShare?app_key=your_appkey_here&method=buyin.doukeCommandParseAndShare&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `command_info` | object | 口令信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 当前口令无效（sub_code: isv.parameter-invalid:4446） | 当前口令无效 |
| `40004` | 非法的参数 / 当前口令无效（sub_code: isv.parameter-invalid:4447） | 当前口令无效 |
| `40004` | 非法的参数 / 无效直播预告口令（sub_code: isv.parameter-invalid:4448） | 无效直播预告口令 |
| `40004` | 非法的参数 / 无效红包口令（sub_code: isv.parameter-invalid:4449） | 无效红包口令 |
| `40004` | 非法的参数 / 无效活动口令（sub_code: isv.parameter-invalid:4450） | 无效活动口令 |
| `40004` | 非法的参数 / 当前口令暂不支持解析（sub_code: isv.parameter-invalid:4451） | 当前口令暂不支持解析 |
| `40004` | 非法的参数 / 无效直播间口令（sub_code: isv.parameter-invalid:4147） | 无效直播间口令 |
| `40004` | 非法的参数 / 无效商品口令（sub_code: isv.parameter-invalid:4148） | 无效商品口令 |
| `20001` | 内部服务超时 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-timeout-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 需对应角色正确授权后访问（sub_code: isv.parameter-invalid:8196） | 需对应角色正确授权后访问 |
| `50002` | 业务处理失败 / 454:无效口令（sub_code: isv.business-failed:454） | 454:无效口令 |
| `50002` | 业务处理失败 / 448:当前口令无效（sub_code: isv.business-failed:448） | 448:当前口令无效 |
| `50002` | 业务处理失败 / 446:当前口令暂不支持解析（sub_code: isv.business-failed:446） | 446:当前口令暂不支持解析 |
| `50002` | 业务处理失败 / 513:当前抖客暂不支持该功能（sub_code: isv.business-failed:513） | 513:当前抖客暂不支持该功能 |
| `50002` | 业务处理失败 / 4132:商品没有加入精选联盟（sub_code: isv.business-failed:4132） | 4132:商品没有加入精选联盟 |
| `50002` | 业务处理失败 / 4133:商品已下架（sub_code: isv.business-failed:4133） | 4133:商品已下架 |
| `50002` | 业务处理失败 / 4097:参数校验失败（sub_code: isv.business-failed:4097） | 4097:参数校验失败 |
| `50002` | 业务处理失败 / 4112:当前达人未开通分销采买业务权限（sub_code: isv.business-failed:4112） | 4112:当前达人未开通分销采买业务权限 |
| `50002` | 业务处理失败 / 449:无效直播间口令（sub_code: isv.business-failed:449） | 449:无效直播间口令 |

## 响应示例

成功：

```json
{
  "data": {
    "command_info": {
      "activity_info": {
        "extra_params": "{\"product_id\":\"12345678\"}\"",
        "material_id": "123456",
        "share_info": {
          "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927",
          "qrcode": {
            "height": "360",
            "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
            "width": "360"
          },
          "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη",
          "zlink": "https://z.douyin.com/xxxxxxx"
        }
      },
      "command_type": "1",
      "live_appoint_info": {
        "author_buyin_id": "112233",
        "live_appointment_id": "123456",
        "share_info": {
          "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927",
          "qrcode": {
            "height": "360",
            "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
            "width": "360"
          },
          "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη"
        }
      },
      "live_info": {
        "author_buyin_id": "112233",
        "product_id": "123456",
        "share_info": {
          "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927",
          "qrcode": {
            "height": "360",
            "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
            "width": "360"
          },
          "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη",
          "zlink": "https://z.douyin.com/xxxxxxx"
        }
      },
      "pid": "\"\"",
      "product_info": {
        "ins_activity_param": "abc",
        "product_id": "123456",
        "share_info": {
          "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927",
          "qrcode": {
            "height": "360",
            "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
            "width": "360"
          },
          "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη",
          "share_link": "https://haohuo.jinritemai.YOUR_SECRET_KEY.html?id=",
          "zlink": "https://z.douyin.com/xxxxxxx"
        }
      },
      "redpack_info": {
        "redpack_id": "123456",
        "share_info": {
          "deeplink": "snssdk1128://ec_goods_detail/?promotion_id=3471556980941674&kol_id=99575927",
          "qrcode": {
            "height": "360",
            "url": "https://p3.douyinpic.com/img/aweme-qrcode/PqFhya700510763792421~c5_360x360.webp?from=1723184",
            "width": "360"
          },
          "share_command": "长按覆[呲牙]zhi此条消息，咑[玫瑰]搜[烟花]，查看商品详情Ig9FOHrrl8ηη"
        }
      }
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4446",
  "sub_msg": "当前口令无效"
}
```

## 备注
