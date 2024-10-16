# 🎶 Unofficial Livecounts.io API

**Unofficial API for Livecounts.io to retrieve live counts for users and videos on TikTok, YouTube, Twitter, Twitch, KickLive, Vlive, and Odysee**

## 📝 Supported APIs

- [x] **YouTube**: User/Video Count
- [x] **TikTok**: User/Video Count
- [x] **Twitter**: User Count

## 🕵️ Usage

```shell
pip install unofficial_livecounts_api
```

### Tiktok API

#### Classes Overview

### `TiktokUser`
Represents a TikTok user.

#### Attributes:
- `user_id` (str): Unique ID of the user.
- `username` (str): Username of the user.
- `display_name` (str): Display name of the user.
- `thumbnail` (str): URL of the user's profile image.
- `verified` (bool): Whether the user is verified.

### `TiktokUserCount`
Contains statistics related to a TikTok user.

#### Attributes:
- `user_id` (str): Unique ID of the user.
- `follower_count` (int): Number of followers.
- `like_count` (int): Number of likes.
- `following_count` (int): Number of users the user is following.
- `video_count` (int): Number of videos posted.

### `TiktokVideo`
Represents a TikTok video.

#### Attributes:
- `video_id` (str): Unique ID of the video.
- `title` (str): Title of the video.
- `thumbnail` (str): URL of the video's thumbnail.
- `user` (TiktokUser): The user who posted the video.

### `TikTokVideoCount`
Contains statistics related to a TikTok video.

#### Attributes:
- `video_id` (str): Unique ID of the video.
- `view_count` (int): Number of views.
- `like_count` (int): Number of likes.
- `comment_count` (int): Number of comments.
- `share_count` (int): Number of shares.

### `TiktokAgent`
A utility class for fetching user and video information.

#### Methods:
- `find_user(query: str) -> list[TiktokUser]`: Find users based on the query.
- `fetch_user_metrics(query: str) -> TiktokUserCount`: Fetch user metrics based on user ID.
- `find_video(query: str) -> TiktokVideo`: Find a video by its ID or URL.
- `fetch_video_metrics(query: str) -> TikTokVideoCount`: Fetch video metrics based on video ID or URL.

- **User API**

```python
from unofficial_livecounts_api.tiktok import TiktokAgent

# Find users
users = TiktokAgent.find_user(query="best")

# Live count a user
user_metric_by_user_id = TiktokAgent.fetch_user_metrics(query="123456789")
```

- **Video API**

```python
from unofficial_livecounts_api.tiktok import TiktokAgent

# Find a video
video_by_query = TiktokAgent.find_video(query="https://tiktok.com/@test/video/122222223233232?test1=value1")
video_by_video_id = TiktokAgent.find_video(query="122222223233232")

# Live count video
video_metric_by_query = TiktokAgent.fetch_video_metrics(query="https://tiktok.com/@test/video/122222223233232?test1=value1")
video_metric_by_video_id = TiktokAgent.fetch_video_metrics(query="122222223233232")
```

### YouTube API

- **User API**

```python
from unofficial_livecounts_api.youtube import YoutubeAgent

# Find channels by given query
channels = YoutubeAgent.find_channel(query="test")

# Live count channel
channel_metrics_by_query = YoutubeAgent.fetch_channel_metrics(query="test")

```

- **Video API**

```python
from unofficial_livecounts_api.youtube import YoutubeAgent

# Find videos by given query
videos = YoutubeAgent.find_video(query="test")

# Live count a video
video_metrics_by_query = YoutubeAgent.fetch_video_metrics(query="123456789")
```

### Twitter API

```python
from unofficial_livecounts_api.twitter import TwitterAgent

# Find users by given query
user = TwitterAgent.find_user(query="jack")

# Live count user
metrics = TwitterAgent.fetch_user_metrics(query="jack")
```

## 📛 Disclaimer

This project aimed to security research, testing purpose. Any misuse of this API for malicious purposes is not condoned.
The developers of this API are not responsible for any illegal or unethical activities carried out using this API.
