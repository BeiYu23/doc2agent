# second.ecomInsight.getTaskResult

> 获取任务结果

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.second.ecomInsight.getTaskResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7930 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `id` | body | mixed | 是 | 任务id | `1` |
| `task_type` | body | string | 是 | 任务类型 | `VideoByText` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.ecomInsight.getTaskResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `msg` | string | 消息 | `success` |
| `code` | mixed | 状态码 | `0` |
| `video_by_text_response` | object | 文生视频返回值 | `` |
| `video_by_pic_first_frame_response` | object | 视频生成-基于首帧 | `` |
| `video_by_pic_first_last_frame_response` | object | 视频生成-基于首尾帧 | `` |
| `video_understand_response` | object | 视频理解 | `` |
| `video_by_pic_ref_and_video_response` | object | VideoPilot返回结构 | `` |
| `pic_by_text_response` | object | 文生图结构 | `` |
| `deep_think_response` | object | 深度思考 | `` |
| `speech_by_text_response` | object | 语音生成 | `` |
| `pic_understand_response` | object | 图片理解 | `` |
| `pic_edit_response` | object | 图片修改 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "deep_think_response": {
      "caching": {
        "type": "disabled"
      },
      "created_at": "xxxx",
      "error": {
        "code": "0",
        "message": "xxxx"
      },
      "expire_at": "xxxx",
      "id": "xxxxx",
      "max_output_tokens": "xxxx",
      "model": "xxxxx",
      "object": "response",
      "output": [
        {
          "content": [
            {
              "text": "xxxx",
              "type": "output_text"
            }
          ],
          "id": "xxxx",
          "role": "assistant",
          "status": "completed",
          "summary": [
            {
              "text": "xxxx",
              "type": "summary_text"
            }
          ],
          "type": "message"
        }
      ],
      "service_tier": "xxxx",
      "status": "completed",
      "text": {
        "format": {
          "type": "xxx"
        }
      },
      "thinking": {
        "type": "enabled"
      },
      "usage": {
        "input_tokens": "xxx",
        "input_tokens_details": {
          "cached_tokens": "xxx"
        },
        "output_tokens": "xxx",
        "output_tokens_details": {
          "reasoning_tokens": "xxx"
        },
        "total_tokens": "xxx"
      }
    },
    "msg": "success",
    "pic_by_text_response": {
      "created": "123123",
      "data": [
        {
          "size": "xxxx",
          "url": "xxx"
        }
      ],
      "model": "xxxx",
      "usage": {
        "completion_tokens": "212123",
        "completion_tokens_details": {
          "cached_tokens": "123123",
          "reasoning_tokens": "123123"
        },
        "prompt_tokens": "123123",
        "prompt_tokens_details": {
          "cached_tokens": "123123",
          "reasoning_tokens": "123123"
        },
        "total_tokens": "123123"
      }
    },
    "pic_edit_response": {
      "created": "xxxxx",
      "data": [
        {
          "b64_json": "xxxxxx",
          "size": "xxxxx",
          "url": "xxxxx"
        }
      ],
      "error": {
        "code": "xx",
        "message": "xxxxx"
      },
      "model": "xxxxx",
      "usage": {
        "generated_images": "1"
      }
    },
    "pic_understand_response": {
      "choices": [
        {
          "finish_reason": "stop",
          "index": "1",
          "message": {
            "content": "xxxxx",
            "name": "xxxx",
            "reasoning_content": "xxxxxx",
            "role": "assistant"
          }
        }
      ],
      "created": "xxxxxx",
      "id": "xxxx",
      "model": "xxxx",
      "object": "chat.completion",
      "service_tier": "xxxxx"
    },
    "speech_by_text_response": {
      "tos_path": "xxxx",
      "words": [
        {
          "confidence": "0.55",
          "end_time": "0.2",
          "start_time": "0.1",
          "word": "三"
        }
      ]
    },
    "video_by_pic_first_frame_response": {
      "file_url": "xxx",
      "last_frame_url": "xxx",
      "video_url": "xxx"
    },
    "video_by_pic_first_last_frame_response": {
      "file_url": "xxx",
      "last_frame_url": "xxx",
      "video_url": "xxx"
    },
    "video_by_pic_ref_and_video_response": {
      "file_url": "xxx",
      "last_frame_url": "xxx",
      "video_url": "xxx"
    },
    "video_by_text_response": {
      "file_url": "xxxx",
      "last_frame_url": "xxx",
      "video_url": "xxx"
    },
    "video_understand_response": {
      "choices": [
        {
          "finish_reason": "stop",
          "index": "1",
          "logprobs": "null",
          "message": {
            "content": "xxxx",
            "reasoning_content": "xxxx",
            "role": "xxxx"
          }
        }
      ],
      "created": "12312312312",
      "id": "1",
      "model": "xxxx",
      "object": "xxx",
      "service_tier": "default",
      "usage": {
        "completion_tokens": "123123",
        "completion_tokens_details": {
          "cached_tokens": "123213",
          "reasoning_tokens": "123123"
        },
        "prompt_tokens": "123123",
        "prompt_tokens_details": {
          "cached_tokens": "123123",
          "reasoning_tokens": "123123"
        },
        "total_tokens": "1231"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
