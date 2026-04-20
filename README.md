# Douyin Video Transcriber - 抖音视频批量转写器

批量下载抖音视频并使用 Whisper 转写为文字文案。

## 功能

- 支持单个视频或博主主页批量转写
- 基于本地 Whisper 模型（无需 API 密钥）
- 按点赞排序取 Top N 条
- 自动生成 Markdown 报告
- 转写完成后自动清理临时文件

## 用法

### 单条视频转写

```bash
python3 scripts/run.py --url "https://www.douyin.com/video/XXXXX"
```

### 博主主页批量转写

```bash
python3 scripts/batch_transcribe.py \
  --profile-url "https://www.douyin.com/user/XXXXX" \
  --top 20
```

## 参数

| 参数 | 说明 |
|------|------|
| `--url` | 抖音视频链接（可多次使用） |
| `--profile-url` | 博主主页URL |
| `--top` | 转写点赞最高的前N条，默认20 |
| `--output-file` | 自定义输出报告路径 |

## 前置条件

- ffmpeg
- OpenAI Whisper (`pip install openai-whisper`)
- Playwright (`pip install playwright`)
- requests (`pip install requests`)
