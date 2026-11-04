# second.ecomInsight.createTask

> 创建task任务接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.createTask` |
| 中文名 | 创建task任务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7935 |
| 更新日期 | `2026-07-23` |

## 接口说明

- 文档书: 短视频API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `video_by_pic_first_frame_request` | body | object | 否 | 视频生成-基于首帧 | `` |
| `  └ first_frame_asset` | body | object | 是 | 首帧素材 | `` |
| `    └ file_element` | body | string | 是 | 文件，内容包括视频url、商品id、图片url、素材id等，根据type传入 | `xxxxxx` |
| `    └ type` | body | string | 是 | asset(素材，fileElement使用素材id)，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `path` |
| `  └ fps` | body | string | 是 | 帧数 | `25` |
| `  └ return_last_frame` | body | boolean | 否 | 是否返回尾帧 | `true` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名（不可重复） | `电商任务1` |
| `    └ task_type` | body | string | 是 | 任务类型 | `VideoByPicFirstFrame` |
| `    └ model` | body | string | 是 | 首帧生成视频支持模型： Doubao-Seedance-1.0-pro-fast | `Doubao-Seedance-1.0-pro-fast` |
| `  └ generate_audio` | body | boolean | 否 | 是否生成对应音频 | `true` |
| `  └ text` | body | string | 是 | 文生视频、图生视频中在text后添加--参数的方式添加对应视频参数（参数必填）。   --rt 比例 --dur 视频时长  --fps 视频帧数  --rs 清晰度  --wm 是否包含水印 -- cf 是否固定摄像头 | `示例：指定生成视频的宽高比为16:9，时长为 5 秒，帧率为 24 fps，分辨率为720p，包含水印，不固定摄像头 一位身穿绿色亮片礼服的女性站在粉红色背景前，周围飘落着五彩斑斓的彩纸 --rt 16:9 --dur 5 --fps 24 --rs 720p --wm true --cf false` |
| `video_by_pic_first_last_frame_request` | body | object | 否 | 视频生成-基于首尾帧 | `` |
| `  └ text` | body | string | 是 | 文生视频、图生视频中在text后添加--参数的方式添加对应视频参数（参数必填）。   --rt 比例 --dur 视频时长  --fps 视频帧数  --rs 清晰度  --wm 是否包含水印 -- cf 是否固定摄像头 | `示例：指定生成视频的宽高比为16:9，时长为 5 秒，帧率为 24 fps，分辨率为720p，包含水印，不固定摄像头 一位身穿绿色亮片礼服的女性站在粉红色背景前，周围飘落着五彩斑斓的彩纸 --rt 16:9 --dur 5 --fps 24 --rs 720p --wm true --cf false` |
| `  └ return_last_frame` | body | boolean | 否 | 是否返回尾帧数 | `true` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名 | `电商任务1` |
| `    └ model` | body | string | 是 | 首尾帧支持模型： Doubao-Seedance-1.0-pro | `Doubao-Seedance-1.0-pro` |
| `    └ task_type` | body | string | 是 | 任务类型 | `VideoByPicFirstLastFrame` |
| `  └ first_frame_asset` | body | object | 是 | 首帧素材 | `` |
| `    └ type` | body | string | 是 | asset(素材，fileElement使用素材id)，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `path` |
| `    └ file_element` | body | string | 是 | 文件，内容包括视频url、商品id、图片url、素材id等，根据type传入 | `xxxx` |
| `  └ last_frame_asset` | body | object | 是 | 尾帧素材 | `` |
| `    └ type` | body | string | 是 | asset(素材，fileElement使用素材id)，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `path` |
| `    └ file_element` | body | string | 是 | 文件，内容包括视频url、商品id、图片url、素材id等，根据type传入 | `xxxxx` |
| `  └ generate_audio` | body | boolean | 否 | 是否返回音频 | `true` |
| `  └ fps` | body | string | 否 | 帧数 | `25` |
| `video_understand_request` | body | object | 否 | 视频理解 | `` |
| `  └ text` | body | string | 是 | 描述 | `视频中有几个人？` |
| `  └ video_asset` | body | object | 是 | 理解视频素材 | `` |
| `    └ file_element` | body | string | 是 | 文件，内容包括视频url、商品id、图片url、素材id等，根据type传入 | `xxxx` |
| `    └ type` | body | string | 是 | asset(素材，fileElement使用素材id)，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `video_id` |
| `  └ standard_prompt` | body | boolean | 否 | 是否使用标准模版输出 | `false` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名 | `xxxxxx` |
| `    └ task_type` | body | string | 是 | 任务类型 | `VideoUnderstand` |
| `    └ model` | body | string | 是 | 视频理解支持模型： Doubao-Seed-1.6-vision | `Doubao-Seed-1.6-vision` |
| `  └ max_tokens` | body | string | 否 | 结果最大tokens，默认4096，最大32000 | `4096` |
| `  └ fps` | body | string | 是 | 视频理解的帧数，会根据输入的帧数抽帧进行视频理解 | `25` |
| `video_by_pic_ref_and_video_request` | body | object | 否 | VideoPilot生成视频参数 | `` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ model` | body | string | 是 | 传入对应model | `无` |
| `    └ task_type` | body | string | 是 | 任务类型 | `VideoByPicRefAndVideo` |
| `    └ name` | body | string | 是 | 任务名 | `xxxxx` |
| `  └ duration` | body | mixed | 否 | 生成视频时长，仅支持整数，单位：秒。 取值范围：[4,15] 或设置为-1(自动适配时长) | `10` |
| `  └ watermark` | body | boolean | 否 | 是否添加水印 | `true` |
| `  └ tools` | body | array | 否 | 使用联网搜索 | `` |
| `    └ type` | body | string | 否 | web_search | `web_search` |
| `  └ return_last_frame` | body | boolean | 否 | 是否返回尾帧 | `true` |
| `  └ generate_audio` | body | boolean | 否 | 是否返回音频 | `true` |
| `  └ resolution` | body | string | 否 | 分辨率: 480p、720p | `720p` |
| `  └ ratio` | body | string | 否 | 生成视频的宽高比例。不同宽高比对应的宽高像素值见下方: - 16:9  - 4:3 - 1:1 - 3:4 - 9:16 - 21:9 - adaptive：根据输入自动选择最合适的宽高比 | `16:9` |
| `  └ content` | body | array | 否 | 请求数据 | `` |
| `    └ attachment_url` | body | object | 否 | 附件 | `` |
| `      └ url` | body | string | 否 | 目前附件只支持公网可访问的pdf文件地址 | `https://ark-project.tos-cn-beijing.volces.com/xxxxx.pdf` |
| `      └ type` | body | string | 否 | 目前类型仅支持输入 path | `path` |
| `    └ role` | body | string | 否 | 图片或者视频的位置或用途。 图片：first_frame（首帧）、last_frame（尾帧）、reference_image（参考图1～9张） 视频：reference_video（参考视频，单个视频时长 [2, 15] s，最多传入 3 个参考视频，所有视频总时长不超过 15s） 音频：reference_audio（单个音频时长 [2, 15] s，最多传入 3 段参考音频，所有音频总时长不超过 15 s） | `reference_video` |
| `    └ image_url` | body | object | 否 | 图片数据 | `` |
| `      └ url` | body | string | 否 | 图片url地址（公网可访问，不可以直接传图片文件） | `xxxx` |
| `    └ audio_url` | body | object | 否 | 音频url信息 | `` |
| `      └ url` | body | string | 否 | 音频url地址（公网可访问，不可以直接传音频文件） | `xxxx` |
| `    └ type` | body | string | 否 | 传入content类型：text（图片）、image_url（图片）、video_url(视频) | `text` |
| `    └ video_url` | body | object | 否 | 视频url信息 | `` |
| `      └ url` | body | string | 否 | 视频url地址（公网可访问，不可以直接传图片文件）、抖音视频id、主图榜单商品id | `xxxx` |
| `      └ type` | body | string | 否 | 根据类型在url中传入对应的信息，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `path` |
| `    └ text` | body | string | 否 | 提示词 | `生成一个视频` |
| `pic_by_text_request` | body | object | 否 | 文生图 | `` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名（不可重复） | `xxxxx` |
| `    └ model` | body | string | 是 | 文生图支持模型： Doubao-Seedream-4.0 | `Doubao-Seedream-4.0` |
| `    └ task_type` | body | string | 是 | 任务类型： PicByText | `PicByText` |
| `  └ sequential_image_generation` | body | string | 是 | 是否生成组图 disabled - 不生成，auto - 生成 | `disabled` |
| `  └ prompt` | body | string | 是 | 需要进行的图片风格的描述 | `生成一张老虎晒太阳的图片` |
| `  └ image` | body | array | 否 | 图片素材 | `` |
| `    └ file_element` | body | string | 否 | 文件，内容包括视频url、商品id、图片url、素材id等，根据type传入 | `xxxxx` |
| `    └ type` | body | string | 否 | asset(素材，fileElement使用素材id)，path（图片或视频url，必须是公网可访问的），video_id（抖音视频id）， product_id（商品id（主图视频）） | `path` |
| `  └ size` | body | string | 是 | 生成图片的大小：2K | `2K` |
| `  └ watermark` | body | boolean | 是 | 是否生成水印 | `true` |
| `video_by_text_request` | body | object | 否 | 文生视频 | `` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名（不可重复） | `xxxxx` |
| `    └ model` | body | string | 是 | 文生视频支持模型： Doubao-Seedance-1.0-pro-fast | `Doubao-Seedance-1.0-pro-fast` |
| `    └ task_type` | body | string | 是 | 任务类型：VideoByText | `VideoByText` |
| `  └ text` | body | string | 是 | 文生视频、图生视频中在text后添加--参数的方式添加对应视频参数（参数必填） --rt 比例、 --dur 视频时长、--fps 视频帧数、--rs 清晰度  --wm 是否包含水印 -- cf 是否固定摄像头 | `指定生成视频的宽高比为16:9，时长为 5 秒，帧率为 24 fps，分辨率为720p，包含水印，不固定摄像头 对应text：一位身穿绿色亮片礼服的女性站在粉红色背景前，周围飘落着五彩斑斓的彩纸 --rt 16:9 --dur 5 --fps 24 --rs 720p --wm true --cf false` |
| `  └ generate_audio` | body | boolean | 否 | 是否返回音频 | `true` |
| `  └ return_last_frame` | body | boolean | 否 | 是否返回尾帧 | `true` |
| `pic_edit_request` | body | object | 否 | 图片修改 | `` |
| `  └ prompt` | body | string | 是 | 文本 | `将图中的小狗替换为一只老虎` |
| `  └ seed` | body | mixed | 是 | 随机数种子，用于控制模型生成内容的随机性。取值范围为 [-1, 2147483647] | `123` |
| `  └ image` | body | string | 是 | 图片文件的url | `https://ark-project.tos-cn-beijing.volces.com/doc_image/seedream4_imageToimage.png` |
| `  └ watermark` | body | boolean | 是 | 是否生成水印 | `true` |
| `  └ guidance_scale` | body | string | 是 | 模型输出结果与prompt的一致程度，生成图像的自由度，又称为文本权重；值越大，模型自由度越小，与用户输入的提示词相关性越强。取值范围1-10 | `7.5` |
| `  └ base` | body | object | 是 | 基础信息 | `` |
| `    └ name` | body | string | 是 | 任务名 | `xxx` |
| `    └ task_type` | body | string | 是 | 任务类型 | `PicEdit` |
| `    └ model` | body | string | 是 | 模型名 | `Doubao-SeedEdit-3.0-i2i` |
| `speech_by_text_request` | body | object | 否 | 语音生成结构 | `` |
| `  └ emotion_scale` | body | string | 否 | 调用emotion设置情感参数后可使用emotion_scale进一步设置情绪值，范围1~5，不设置时默认值为4。 注：理论上情绪值越大，情感越明显。但情绪值1~5实际为非线性增长，可能存在超过某个值后，情绪增加不明显，例如设置3和5时情绪值可能接近。 | `4` |
| `  └ speech_rate` | body | string | 否 | 语速，取值范围[-50,100]，100代表2.0倍速，-50代表0.5倍数，默认值0 | `0` |
| `  └ context_texts` | body | array | 否 | 语音合成的辅助信息，用于模型对话式合成，能更好的体现语音情感； 可以探索，比如常见示例有以下几种： 1. 语速调整   1. 比如：context_texts: ["你可以说慢一点吗？"] 2. 情绪/语气调整   1. 比如：context_texts=["你可以用特别特别痛心的语气说话吗?"]   2. 比如：context_texts=["嗯，你的语气再欢乐一点"] 3. 音量调整   1. 比如：context_texts=["你嗓门再小点。"] 4. 音感调整   1. 比如：context_texts=["你能用骄傲的语气来说话吗？"] 注意： 1. 该字段仅适用于"豆包语音合成模型2.0"的音色 2. 当前字符串列表只第一个值有效 3. 该字段文本不参与计费 | `["你可以说慢一点吗？"]` |
| `  └ section_id` | body | string | 否 | 其他合成语音的会话id(session_id)，用于辅助当前语音合成，提供更多的上下文信息； 取值，参见接口交互中的session_id 示例： 1. section_id="bf5b5771-31cd-4f7a-b30c-f4ddcbf2f9da" 注意： 1. 该字段仅适用于"豆包语音合成模型2.0"的音色 2. 历史上下文的session_id 有效期：   1. 最长30轮   2. 最长10分钟 | `xxxx` |
| `  └ base` | body | object | 是 | 基础参数 | `` |
| `    └ task_type` | body | string | 是 | 任务类型 | `SpeechByText` |
| `    └ name` | body | string | 是 | 任务名 | `xxxx` |
| `    └ model` | body | string | 是 | 模型：Seed-TTS-2.0 Seed-TTS-1.0 | `Seed-TTS-2.0` |
| `  └ context_language` | body | string | 否 | - 不给定 西欧语种采用英语 - id 西欧语种采用印尼 - es 西欧语种采用墨西 - pt 西欧语种采用巴葡 | `pt` |
| `  └ unsupported_char_ratio_thresh` | body | string | 否 | 默认: 0.3，最大值: 1.0 检测出不支持合成的文本超过设置的比例，则会返回错误。 | `0.3` |
| `  └ silence_duration` | body | string | 否 | 设置该参数可在句尾增加静音时长，范围0~30000ms。（注：增加的句尾静音主要针对传入文本最后的句尾，而非每句话的句尾），默认值0 | `0` |
| `  └ loudness_rate` | body | string | 否 | 音量，取值范围[-50,100]，100代表2.0倍音量，-50代表0.5倍音量（mix音色暂不支持），默认值0 | `0` |
| `  └ post_process_pitch` | body | string | 否 | 音调取值范围是[-12,12]，默认0 | `0` |
| `  └ emotion` | body | string | 否 | 情感设置，可设置angry等，https://www.volcengine.com/docs/6561/1257544?lang=zh | `shy` |
| `  └ encoding` | body | string | 否 | 音频编码格式，mp3/ogg_opus/pcm，默认mp3 | `mp3` |
| `  └ enable_language_detector` | body | boolean | 否 | 自动识别语种，默认值false | `false` |
| `  └ max_length_to_filter_parenthesis` | body | mixed | 否 | 是否过滤括号内的部分，0为不过滤，100为过滤，默认值100 | `100` |
| `  └ aigc_watermark` | body | boolean | 否 | 默认：false 是否在合成结尾增加音频节奏标识 | `false` |
| `  └ disable_emoji_filter` | body | boolean | 否 | 开启emoji表情在文本中不过滤显示，默认为false，建议搭配时间戳参数一起使用。 | `false` |
| `  └ sample_rate` | body | string | 否 | 音频采样率，可选值 [8000,16000,22050,24000,32000,44100,48000]，默认值24000 | `24000` |
| `  └ text` | body | string | 是 | 文本 | `xxxx` |
| `  └ bit_rate` | body | string | 否 | 音频比特率，可传16000、32000等。bit_rate默认设置范围为64k～160k，默认值8000 | `8000` |
| `  └ explicit_language` | body | string | 否 | - 不给定参数，启用多语种前端zh,en,ja,es-mx,id,pt-br,de,fr - zh,en,ja,es-mx,id,pt-br,de,fr 启用多语种前端 - zh-cn 中文为主，支持中英混 - en 仅英文 - ja 仅日文 - es-mx 仅墨西 - id 仅印尼 - pt-br 仅巴葡 - de 仅德语 - fr 仅法语 | `zh` |
| `  └ aigc_metadata_enable` | body | boolean | 否 | 是否启用隐式水印，默认false | `false` |
| `  └ voice` | body | string | 是 | 嗓音支持2.0部分语言，https://www.volcengine.com/docs/6561/1257544?lang=zh | `zh_female_vv_uranus_bigtts` |
| `  └ disable_markdown_filter` | body | boolean | 否 | 是否开启markdown解析过滤， 为true时，解析并过滤markdown语法，例如，你好，会读为“你好”， 为false时，不解析不过滤，例如，你好，会读为“星星‘你好’星星”，默认值false | `false` |
| `pic_understand_request` | body | object | 否 | 图片理解 | `` |
| `  └ max_tokens` | body | string | 否 | 结果最大tokens，默认4096，最大32000 | `4096` |
| `  └ detail` | body | string | 是 | - low：“低分辨率”模式，处理速度会提高，适合图片本身细节较少或者只需模型理解图片大致信息或者对速度有要求的场景。 - high：“高分辨率”模式，模型可感知图片更多的细节，但是处理图片速度会降低，适合图像像素值高且需关注细节信息的场景，如街道地图分析等。 | `low` |
| `  └ image` | body | string | 否 | 图片url，image或images参数最少一个有数据 | `xxxx` |
| `  └ images` | body | array | 否 | 图片url集合，image或images参数最少一个有数据 | `[xxxx,xxxx]` |
| `  └ base` | body | object | 是 | 基础参数 | `` |
| `    └ name` | body | string | 是 | 任务名 | `xxx` |
| `    └ task_type` | body | string | 是 | 任务类型 | `PicUnderstand` |
| `    └ model` | body | string | 是 | 模型 | `Doubao-Seed-1.6` |
| `  └ text` | body | string | 是 | 文本 | `图中的动物是什么？` |
| `deep_think_request` | body | object | 否 | 深度思考 | `` |
| `  └ previous_response_id` | body | string | 否 | 上次深度思考返回的id | `xxxxx` |
| `  └ messages` | body | array | 否 | message消息结构 | `` |
| `    └ role` | body | string | 否 | 角色： 输入消息的角色，可以是 user，system ，assistant或 developer。 | `user` |
| `    └ content` | body | array | 否 | 内容结构 | `` |
| `      └ video_url` | body | object | 否 | 视频参数结构 | `` |
| `        └ url` | body | string | 否 | 视频文件url | `https://ark-project.tos-cn-beijing.volces.com/xxxxx.mp4` |
| `        └ fps` | body | string | 否 | 视频理解的帧数，会根据输入的帧数抽帧进行视频理解 | `25` |
| `      └ type` | body | string | 否 | 消息输入的类型， image_url、text、video_url | `text` |
| `      └ image_url` | body | object | 否 | 图片参数结构 | `` |
| `        └ url` | body | string | 否 | 图片文件url | `https://ark-project.tos-cn-beijing.volces.com/doc_image/ark_demo_img_1.png` |
| `        └ detail` | body | string | 否 | - low：“低分辨率”模式，处理速度会提高，适合图片本身细节较少或者只需模型理解图片大致信息或者对速度有要求的场景。 - high：“高分辨率”模式，模型可感知图片更多的细节，但是处理图片速度会降低，适合图像像素值高且需关注细节信息的场景，如街道地图分析等。 | `high` |
| `      └ text` | body | string | 否 | type为text类型时，使用的文本 | `文艺复兴三杰是？` |
| `      └ attachment_url` | body | object | 否 | 附件 | `` |
| `        └ type` | body | string | 否 | 目前类型仅支持path | `path` |
| `        └ url` | body | string | 否 | 只能是公网可访问的pdf文件链接 | `https://ark-project.tos-cn-beijing.volces.com/xxxxx.pdf` |
| `  └ base` | body | object | 是 | 基础参数 | `` |
| `    └ name` | body | string | 是 | 任务名 | `xxxx` |
| `    └ task_type` | body | string | 是 | 任务类型 | `DeepThink` |
| `    └ model` | body | string | 是 | Doubao-Seed-1.6-thinking, Doubao-Seed-1.6-flash | `Doubao-Seed-1.6-thinking` |
| `  └ text` | body | string | 否 | 文本 | `xxx` |
| `  └ max_tokens` | body | string | 否 | 结果最大tokens，默认4096，最大32000 | `4096` |
| `  └ reasoning` | body | string | 否 | 限制深度思考的工作量。减少深度思考工作量可使响应速度更快，并且深度思考的 token 用量更小。 minimal：关闭思考，直接回答。 low：轻量思考，侧重快速响应。 medium：均衡模式，兼顾速度与深度。 high：深度分析，处理复杂问题。 仅模型 doubao-seed-1-8-251228、doubao-seed-1-6-lite-251015、doubao-seed-1-6-251015 支持该字段。 | `medium` |
| `  └ thinking` | body | string | 是 | disabled：强制关闭深度思考能力，模型不输出思维链内容。 enabled：强制开启深度思考能力，模型强制输出思维链内容。 Doubao-Seed-1.6-thinking只支持enabled Doubao-Seed-1.6-flash支持enabled或disabled auto：模型自行判断是否需要进行深度思考。 | `enabled` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.createTask&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回结构体 | `` |
| `msg` | string | 消息 | `xxxx` |
| `code` | mixed | 状态码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 处理失败（sub_code: isv.business-failed:400） | 查看具体报错信息 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "create_info": "xxxx",
      "create_time": "xxxxx",
      "id": "123",
      "model_task_id": "xxxx",
      "msg": "success",
      "name": "xxxx",
      "pilot_task_id": "xxx",
      "status": "0",
      "task_result": "xxxx",
      "task_type": "VideoByText",
      "update_time": "xxxx"
    },
    "msg": "xxxx"
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
  "sub_code": "isv.business-failed:400",
  "sub_msg": "处理失败"
}
```

## 备注
