# 部分编辑商品信息

> product.partialEdit — 部分编辑商品信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 部分编辑商品信息 |
| 文档地址 | `/docs/doudian/product/product-product-partialEdit` |
| 接口 ID | `doudian.product.product.partialEdit` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/partialEdit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2694 |
| 更新日期 | `2026-07-14` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品id | `31314511114124151` |
| `name` | body | string | 否 | 商品名称 | `半身裙111` |
| `shop_category` | body | object | 否 | 店铺分类参数 | `` |
| `  └ leaf_category_ids` | body | array | 否 | 店铺叶子分类id，为[]表示清空商品店铺分类。【已废弃，请使用店铺装修侧，/shop/marketCategoryOpsProd 接口修改商品装修分类】 | `[7184320140241125691,             7184320140241142075,             7184320198915129659,             7184320198915146043]` |
| `short_product_name` | body | string | 否 | 商品短标题 | `aaa` |
| `title_info` | body | object | 否 | 标题前缀，可通过/product/getRecommendName接口获取 | `` |
| `  └ prefix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题前缀（注意系统根据类目属性生成前缀字符串时，末尾可能有一个空格） | `钛钢木质耳饰` |
| `  └ suffix` | body | string | 否 | 通过/product/getRecommendName接口推荐的商品标题后缀（注意系统根据类目属性生成后缀字符串时，前面可能有一个空格） | `36.9度` |
| `outer_product_id` | body | string | 否 | 商品外部编码 | `bbb` |
| `delivery_time_info` | body | object | 否 | 商品发货时间信息，当前仅支持sku维度发货时效更新，仅限现货发货模式。 | `` |
| `  └ sku_ship_times` | body | array | 否 | sku发货时间，注意该参数仅在现货发货模式且开启sku发货时效时有效，如果发货模式不符合要求则会校验报错。 发货时间和 commit_code 可分别单独更新，也可一起更新。多sku更新时，保证同时成功或失败。如果传入的skuId在商品下不存在，或者skuId存在重复，将报错。 | `` |
| `    └ ship_time_type` | body | mixed | 否 | 1 相对时间 ships in x days，2 固定日期 fixed date。更新ship_time时必传。 | `1` |
| `    └ commit_code` | body | string | 否 | commit code | `3000` |
| `    └ ship_time` | body | string | 否 | 发货时间，如果是相对时间，填写数据 X。如果是固定日期，填写格式为yyyy-MM-dd，例如 "2025-09-01"。格式不正确或者时间校验不通过，将报错。 | `2` |
| `    └ sku_id` | body | mixed | 否 | skuId | `3508769879052802` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/partialEdit?app_key=your_appkey_here&method=product.partialEdit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 非法参数（sub_code: isv.parameter-invalid:2010004） | 请检查参数后重试 |
| `60000` | 触发限流，请稍后重试 / 更新商品太频繁，操作失败请重试（sub_code: isp.traffic-limited:2010067） | 稍后重试 |
| `40002` | 缺少必选参数 / 缺少参数（sub_code: isv.missing-parameter:2010003） | 重新进入页面进行补充 |
| `50002` | 业务处理失败 / 该商品在审核中（sub_code: isv.business-failed:2010041） | 不允许编辑 |
| `50002` | 业务处理失败 / 该商品已删除（sub_code: isv.business-failed:2010042） | 不允许编辑 |
| `50002` | 业务处理失败 / 该商品已封禁（sub_code: isv.business-failed:2010043） | 不允许编辑 |
| `20000` | 系统错误（sub_code: isp.service-error:2010001） | 稍后重试 |
| `20000` | 系统错误 / 请求超时（sub_code: isp.service-error:2010002） | 稍后重试 |
| `40004` | 非法的参数 / 无访问权限（sub_code: isv.parameter-invalid:2010005） | 核对后重试 |
| `40004` | 非法的参数 / 编辑商品失败（sub_code: isv.parameter-invalid:2010011） | 稍后重试 |
| `20000` | 系统错误 / 保存商品失败（sub_code: isp.service-error:2010012） | 稍后重试 |
| `20000` | 系统错误 / 读取失败（sub_code: isp.service-error:2010013） | 稍后重试 |
| `50002` | 业务处理失败 / 商品状态错误（sub_code: isv.business-failed:2010022） | 检查状态后重试 |
| `50002` | 业务处理失败 / 商品正在参加活动（sub_code: isv.business-failed:2010045） | 暂不支持修改 |
| `20000` | 系统错误 / 获取类目信息失败（sub_code: isp.service-error:2010201） | 重试 |
| `20000` | 系统错误 / 获取类目配置失败（sub_code: isp.service-error:2010202） | 重试 |
| `20000` | 系统错误 / 查询品牌库失败（sub_code: isp.service-error:2010206） | 重试 |
| `20000` | 系统错误 / 查询商家资质失败（sub_code: isp.service-error:2010207） | 查询商家资质失败，请重试 |
| `50002` | 业务处理失败 / 2010501:商品标题未明确描述商品品名，请重新填写（sub_code: isv.business-failed:2010501） | 商品标题未明确描述商品品名，请重新填写 |
| `50002` | 业务处理失败 / 2010326:因为店铺受到处置，限制发品，更多请到商家后台奖惩中心查看（sub_code: isv.business-failed:2010326） | 因为店铺受到处置，限制发品，更多请到商家后台奖惩中心查看 |
| `50002` | 业务处理失败 / 2010316:该类目需要支持7天无理由退货（sub_code: isv.business-failed:2010316） | 因为店铺受到处置，限制发品，更多请到商家后台奖惩中心查看 |
| `50002` | 业务处理失败 / 110214003:分组操作失败：category_id(7209859568560554243)不存在,请核查（sub_code: isv.business-failed:110214003） | 110214003:分组操作失败：category_id(7209859568560554243)不存在,请核查 |
| `50002` | 业务处理失败 / 110101150:商品标题最长不能超过30个汉字（60个字符）（sub_code: isv.business-failed:110101150） | 110101150:商品标题最长不能超过30个汉字（60个字符） |
| `50002` | 业务处理失败 / 2010102:系统检测审核不通过，内容未做修改，请修改后提交审核（sub_code: isv.business-failed:2010102） | 2010102:系统检测审核不通过，内容未做修改，请修改后提交审核 |
| `50002` | 业务处理失败 / 2010058:商品不存在（sub_code: isv.business-failed:2010058） | 2010058:商品不存在 |
| `50002` | 业务处理失败 / 110102123:open侧暂不允许设置分销商品（sub_code: isv.business-failed:110102123） | 110102123:open侧暂不允许设置分销商品 |
| `50002` | 业务处理失败 / 2010320:品牌必填，请重新选择品牌（sub_code: isv.business-failed:2010320） | 2010320:品牌必填，请重新选择品牌 |
| `50002` | 业务处理失败 / 2010318:当前商品选择的品牌信息已过期，请更新品牌资质信息，或更换商品品牌后，再提交商品发布。（sub_code: isv.business-failed:2010318） | 2010318:当前商品选择的品牌信息已过期，请更新品牌资质信息，或更换商品品牌后，再提交商品发布。 |
| `50002` | 业务处理失败 / 110270180:校验预售发货信息失败暂不支持该发货模式（sub_code: isv.business-failed:110270180） | 110270180:校验预售发货信息失败暂不支持该发货模式 |
| `50002` | 业务处理失败 / 2010329:当前店铺类型下, 使用/品牌，需要去资质中心上传品牌资质。去上传>https://zjsms.com/NEvh47E/（sub_code: isv.business-failed:2010329） | 2010329:当前店铺类型下, 使用/品牌，需要去资质中心上传品牌资质。去上传>https://zjsms.com/NEvh47E/ |
| `50002` | 业务处理失败 / 110102129:当前商品仅支持在百应后台编辑（sub_code: isv.business-failed:110102129） | 110102129:当前商品仅支持在百应后台编辑 |
| `50002` | 业务处理失败 / 110101145:“商品标题”不可含有换行符（sub_code: isv.business-failed:110101145） | 110101145:“商品标题”不可含有换行符 |
| `50002` | 业务处理失败 / 110330102:请修改“售后服务“，该类目已不再支持该售后政策（sub_code: isv.business-failed:110330102） | 110330102:请修改“售后服务“，该类目已不再支持该售后政策 |
| `50002` | 业务处理失败 / 110370101:商品属性[面料成分含量]填写格式不正确，不支持发布（sub_code: isv.business-failed:110370101） | 110370101:商品属性[面料成分含量]填写格式不正确，不支持发布 |
| `50002` | 业务处理失败 / 110260145:当前选择的货品(7428984621309657395)不存在，请重新选择货品完成商货品绑定，或删除货品取消绑定，维护商品库存信息。（sub_code: isv.business-failed:110260145） | 110260145:当前选择的货品(7428984621309657395)不存在，请重新选择货品完成商货品绑定，或删除货品取消绑定，维护商品库存信息。 |
| `50002` | 业务处理失败 / 2010339:存在审批中素材(主图视频)，请等待审批（sub_code: isv.business-failed:2010339） | 2010339:存在审批中素材(主图视频)，请等待审批 |
| `50002` | 业务处理失败 / 110405001:该商品商详页描述（含标题、主图和商品详情）与属性栏选择的材质不一致，请修改。规则详见https://school.jinritemai.com/doudian/web/question/50（sub_code: isv.business-failed:110405001） | 110405001:该商品商详页描述（含标题、主图和商品详情）与属性栏选择的材质不一致，请修改。规则详见https://school.jinritemai.com/doudian/web/question/50 |
| `50002` | 业务处理失败 / 110101131:短标题必须在4~12个字（sub_code: isv.business-failed:110101131） | 110101131:短标题必须在4~12个字 |
| `50002` | 业务处理失败 / 110102120:无法直接通过该接口创建或编辑有价券类商品（sub_code: isv.business-failed:110102120） | 110102120:无法直接通过该接口创建或编辑有价券类商品 |
| `50002` | 业务处理失败 / 110270179:校验预售发货信息失败发货时间配置不满足要求（sub_code: isv.business-failed:110270179） | 110270179:校验预售发货信息失败发货时间配置不满足要求 |
| `50002` | 业务处理失败 / 110270110:运费模板不存在（sub_code: isv.business-failed:110270110） | 110270110:运费模板不存在 |
| `50002` | 业务处理失败 / 2010063:为保障消费者权益，“0元入驻”试运营期间的商家店铺会进行发品数量的限制，商品已达上限，暂不支持添加商品，您可通过【抖店-资金-店铺保证金】缴纳保证金至足额后继续此操作，相关详情可查阅《抖音电商“0元入驻”试运营规范》。（sub_code: isv.business-failed:2010063） | 2010063:为保障消费者权益，“0元入驻”试运营期间的商家店铺会进行发品数量的限制，商品已达上限，暂不支持添加商品，您可通过【抖店-资金-店铺保证金】缴纳保证金至足额后继续此操作，相关详情可查阅《抖音电商“0元入驻”试运营规范》。 |
| `50002` | 业务处理失败 / 110290001:请上传食品生产许可证（sub_code: isv.business-failed:110290001） | 110290001:请上传食品生产许可证 |
| `50002` | 业务处理失败 / 2010055:因服务器升级，商品价格展示可能异常，请修改价格后重试（sub_code: isv.business-failed:2010055） | 2010055:因服务器升级，商品价格展示可能异常，请修改价格后重试 |
| `50002` | 业务处理失败 / 110250121:尺码表需包含所有规格中的尺码，请补充尺码（sub_code: isv.business-failed:110250121） | 110250121:尺码表需包含所有规格中的尺码，请补充尺码 |
| `50002` | 业务处理失败 / 110270139:商品关联未结束的限时特卖活动，仅支持现货发货模式和阶梯发货模式（sub_code: isv.business-failed:110270139） | 110270139:商品关联未结束的限时特卖活动，仅支持现货发货模式和阶梯发货模式 |
| `50002` | 业务处理失败 / 110240102:库存数量支持范围：0-10000000（sub_code: isv.business-failed:110240102） | 110240102:库存数量支持范围：0-10000000 |
| `50002` | 业务处理失败 / 110250118:尺码模板不支持当前类目（sub_code: isv.business-failed:110250118） | 110250118:尺码模板不支持当前类目 |
| `50002` | 业务处理失败 / 110270152:校验预售发货信息失败预售结束时间小于当前时间（sub_code: isv.business-failed:110270152） | 110270152:校验预售发货信息失败预售结束时间小于当前时间 |
| `50002` | 业务处理失败 / 110220210:commit code不合法（sub_code: isv.business-failed:110220210） | 110220210:commit code不合法 |
| `50002` | 业务处理失败 / 110360101：品牌不存在或者未审核通过（sub_code: isv.business-failed:110360101） | 110360101：品牌不存在或者未审核通过 |
| `50002` | 业务处理失败 / 110201001：未查询到该类目（sub_code: isv.business-failed:110201001） | 110201001：未查询到该类目 |
| `50002` | 业务处理失败 / 110101267：商品草稿删除失败，请重试（sub_code: isv.business-failed:110101267） | 110101267：商品草稿删除失败，请重试 |
| `50002` | 业务处理失败 / 110502052:商品未发布，不支持编辑，请先发布商品（sub_code: isv.business-failed:110502052） | 110502052:商品未发布，不支持编辑，请先发布商品 |
| `50002` | 业务处理失败 / 110330124:该商品必须配置三包服务承诺（sub_code: isv.business-failed:110330124） | 110330124:该商品必须配置三包服务承诺 |
| `50002` | 业务处理失败 / 110250169:该类目要求上传尺码组件信息，请补充后提交（sub_code: isv.business-failed:110250169） | 110250169:该类目要求上传尺码组件信息，请补充后提交 |
| `50002` | 业务处理失败 / 110250165:尺码表中的尺码大小需与尺码规格保持一致（sub_code: isv.business-failed:110250165） | 110250165:尺码表中的尺码大小需与尺码规格保持一致 |
| `50002` | 业务处理失败 / 110360108:品牌资质规则查询失败（sub_code: isv.business-failed:110360108） | 110360108:品牌资质规则查询失败 |
| `50002` | 业务处理失败 / 110405002:系统异常（sub_code: isv.business-failed:110405002） | 110405002:系统异常 |
| `50002` | 业务处理失败 / 110250016:主图：第 1、5 张不符合格式要求，请上传 JPG/JPEG/PNG 格式，<a href='https://bytedance.larkoffice.com/wiki/Dn0twtf5kiBGr3km7gWc1XjInvg' target='_blank'>文件格式要求/转换方式请参考</a>（sub_code: isv.business-failed:110250016） | 110250016:主图：第 1、5 张不符合格式要求，请上传 JPG/JPEG/PNG 格式，<a href='https://bytedance.larkoffice.com/wiki/Dn0twtf5kiBGr3km7gWc1XjInvg' target='_blank'>文件格式要求/转换方式请参考</a> |
| `50002` | 业务处理失败 / 110210108:识别到商品类目填写错误,请及时修改类目（sub_code: isv.business-failed:110210108） | 110210108:识别到商品类目填写错误,请及时修改类目 |
| `50002` | 业务处理失败 / 110101214:商品因处置下架且未修改商品信息，请先修改商品再重新提交上架（sub_code: isv.business-failed:110101214） | 110101214:商品因处置下架且未修改商品信息，请先修改商品再重新提交上架 |
| `50002` | 业务处理失败 / 110101116:前缀不匹配（sub_code: isv.business-failed:110101116） | 110101116:前缀不匹配 |
| `50002` | 业务处理失败 / 110330125:三包服务类型不合法（sub_code: isv.business-failed:110330125） | 110330125:三包服务类型不合法 |
| `50002` | 业务处理失败 / 110250142:该类目要求尺码组件含衣长、胸围、肩宽、袖长，请补充后提交（sub_code: isv.business-failed:110250142） | 110250142:该类目要求尺码组件含衣长、胸围、肩宽、袖长，请补充后提交 |

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
  "sub_code": "isv.parameter-invalid:2010004",
  "sub_msg": "非法参数"
}
```

## 备注
