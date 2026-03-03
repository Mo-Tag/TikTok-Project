# TikTok Dataset – Data Dictionary

| Column Name              | Data Type    | Description |
|--------------------------|--------------|-----------|
| `claim_status`           | object       | Whether the video is a **claim** (potentially misleading) or **opinion** (personal viewpoint) |
| `video_id`               | int64        | Unique identifier for each video |
| `video_duration_sec`     | int64        | Length of the video in seconds (5–60) |
| `video_transcription_text` | object     | Auto-generated transcription of the video audio |
| `verified_status`        | object       | Whether the author is **verified** or **not verified** |
| `author_ban_status`      | object       | Author's current status: **active**, **under review**, or **banned** |
| `video_view_count`       | float64      | Total number of views the video received |
| `video_like_count`       | float64      | Total number of likes |
| `video_comment_count`    | float64      | Total number of comments |
| `video_share_count`      | float64      | Total number of shares |
| `video_download_count`   | float64      | Total number of downloads |

**Note:** Engagement columns (`view_count`, `like_count`, etc.) are heavily right-skewed, which is typical for social media data.
