<h1 align="center">ARK Message Generation Interface Documentation</h1>
<div align="center">

<p align="center">
    <h3>With this API, you can generate and sign most of the cards available on the market, suitable for use with QQ.</h3>
    <p align="center">
        <a href="https://t.me/cwuoms_group">
<img alt="JoinTelegramGroup" src="https://img.shields.io/badge/Telegram-Group-blue" />
</a>
<p>

  [简体中文](README.md) | **&gt; English &lt;** 
  
</div>

# Interface Information
### This document provides detailed information about the ARK message generation interface, supporting requests via POST and GET methods.
- Interface URL: `https://ark.cwuom.love`
- Currently in testing and fully open, long-term availability is not guaranteed, and interface authentication may be added in the future.

## Usage Instructions
### 1. Large Image ARK Card (`/get_card`)

- **Interface Path:** `/get_card`
- **Request Methods:** POST / GET
- **Request Parameters:**

  | Parameter | Type   | Required | Description     |
  | --------- | ------ | -------- | --------------- |
  | title     | string | 🔴       | Card title      |
  | subtitle  | string | 🔴       | Card subtitle   |
  | prompt    | string | 🔴       | Card display    |
  | cover     | string | 🟢       | Preview image URL |

- **Request Body:**

```json
  {
    "title": "Title",
    "subtitle": "https://api.lyhc.top/bot/a.jpg",
    "prompt": "Display",
    "cover": "https://api.lyhc.top/bot/a.jpg"
  }
```

- **GET Request Example:**

```
https://ark.cwuom.love/get_card?title=Title&subtitle=Subtitle&prompt=Card Display&cover=https://api.lyhc.top/bot/a.jpg
```

- **Response:**

```json
  {
    "app": "com.tencent.imagetextbot",
    "config": {
      "autosize": 1,
      "ctime": 1711208517,
      "token": "09c8985817f3f66f7af047a6392b57aa"
    },
    "meta": {
      "robot": {
        "cover": "https://api.lyhc.top/bot/show?url=https://api.lyhc.top/bot/a.jpg",
        "jump_url": "",
        "subtitle": "https://api.lyhc.top/bot/a.jpg",
        "title": "Title"
      }
    },
    "prompt": "Display",
    "ver": "1.0.0.14",
    "view": "index"
  }
```

### 2. Share Type ARK Card (`/get_card_news`)

- **Interface Path:** `/get_card_news`
- **Request Methods:** POST / GET
- **Request Parameters:**

  | Parameter | Type   | Required | Description       |
  | --------- | ------ | -------- | ----------------- |
  | desc      | string | 🔴       | Card description  |
  | preview   | string | 🟢       | Preview image URL |
  | tag       | string | 🔴       | Tag text          |
  | tagIcon   | string | 🟢       | Tag icon URL      |
  | title     | string | 🔴       | Card title        |
  | prompt    | string | 🔴       | Card display      |
  | uin       | string | 🟢       | uin               |
  | skey      | string | 🟢       | skey              |
  | pSkey     | string | 🟢       | p_skey            |

- **Request Body:**

```json
  {
    "desc": "Card description",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "tag": "Card tag",
    "tagIcon": "https://api.lyhc.top/bot/a.jpg",
    "title": "Card title",
    "prompt": "Display",
    "uin": "o2594748568",
    "skey": "@rbVjLgTMH",
    "pSkey": "BiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyIE3II3M_"
  }
```

- **GET Request Example:**

```
https://ark.cwuom.love/get_card_news?desc=Card description&preview=https://api.lyhc.top/bot/a.jpg&tag=Card tag&tagIcon=https://api.lyhc.top/bot/a.jpg&title=Card title&prompt=Display&uin=o2594748568&skey=@rbVjLgTMH&pSkey=BiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyIE3II3M_
```

- **Response:**

```json
  {
    "app": "com.tencent.qqgxh.general",
    "config": {
      "autosize": 0,
      "ctime": 1711104666,
      "forward": 1,
      "token": "22dd52427614a2aacbc35eb2ad9ee969",
      "type": "normal"
    },
    "meta": {
      "news": {
        "desc": "Card description",
        "jumpUrl": "",
        "preview": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef846c2520/0",
        "tag": "Card tag",
        "tagIcon": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef846c2520/0",
        "title": "Card title"
      }
    },
    "prompt": "Display",
    "view": "news"
  }
```

### 3. Embed Card (`/get_card_embed`)

- **Interface Path:** `/get_card_embed`
- **Request Methods:** POST / GET
- **Request Parameters:**

  | Parameter    | Type   | Required | Description       |
  | ------------ | ------ | -------- | ----------------- |
  | title        | string | 🔴       | Card title        |
  | prompt       | string | 🔴       | Card display      |
  | thumbnailUrl | string | 🔴       | Thumbnail image URL |
  | f1           | string | 🔴       | Field 1 content   |
  | f2           | string | 🔴       | Field 2 content   |
  | f3           | string | 🔴       | Field 3 content   |
  | f4           | string | 🔴       | Field 4 content   |
  | f5           | string | 🔴       | Field 5 content   |

- **Request Body:**

```json
  {
    "title": "Embed card title",
    "prompt": "Display",
    "thumbnailUrl": "https://api.lyhc.top/bot/a.jpg",
    "f1": "Field 1",
    "f2": "Field 2",
    "f3": "Field 3",
    "f4": "Field 4",
    "f5": "Field 5"
  }
```

- **GET Request Example:**

```
https://ark.cwuom.love/get_card_embed?title=Embed card title&prompt=Display&thumbnailUrl=https://api.lyhc.top/bot/a.jpg&f1=Field 1&f2=Field 2&f3=Field 3&f4=Field 4&f5=Field 5
```

- **Response:**

```json
  {
    "app": "com.tencent.bot.groupbot",
    "config": {
      "ctime": 1711208520,
      "token": "9a0f7b57a129388385c1bf8209c052a0",
      "type": "normal"
    },
    "meta": {
      "embed": {
        "fields": [
          {"name": "Field 1"},
          {"name": "Field 2"},
          {"name": "Field 3"},
          {"name": "Field 4"},
          {"name": "Field 5"}
        ],
        "thumbnail": {"url": "https://api.lyhc.top/bot/a.jpg"},
        "title": "Embed card title"
      }
    },
    "prompt": "Display",
    "ver": "1.0.0.9",
    "view": "index"
  }
```

### 5. Miniapp ARK Card (`/get_miniapp_card`)

- **Interface Path:** `/get_miniapp_card`
- **Request Methods:** POST / GET
- **Request Parameters:**

  | Parameter | Type   | Required | Description           |
  | --------- | ------ | -------- | --------------------- |
  | prompt    | string | 🔴       | Card display          |
  | jumpUrl   | string | 🔴       | Jump link             |
  | preview   | string | 🟢       | Preview image URL     |
  | tag       | string | 🔴       | Tag                   |
  | tagIcon   | string | 🟢       | Tag icon URL          |
  | title     | string | 🔴       | Miniapp card title    |
  | uin       | string | 🟢       | uin                   |
  | skey      | string | 🟢       | skey                  |
  | pSkey     | string | 🟢       | p_skey                |

- **Request Body:**

```json
  {
    "prompt": "Display",
    "jumpUrl": "https://api.lyhc.top/bot/a.jpg",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "tag": "Tag",
    "tagIcon": "https://api.lyhc.top/bot/a.jpg",
    "title": "Miniapp card title",
    "uin": "o2594748568",
    "skey": "@rbHjPfTMH",
    "pSkey": "rfHjlfTMBiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3L_"
  }
```

- **GET Request Example:**

```
https://ark.cwuom.love/get_miniapp_card?prompt=Display&jumpUrl=https://api.lyhc.top/bot/a.jpg&preview=https://api.lyhc.top/bot/a.jpg&tag=Tag&tagIcon=https://api.lyhc.top/bot/a.jpg&title=Miniapp card title&uin=o2594748568&skey=@rbHjPfTMH&pSkey=rfHjlfTMBiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3L_
```

- **Response:**

```json
  {
    "actionData": "",
    "actionData_A": "",
    "app": "com.tencent.qqgxh.general",
    "appID": "",
    "bizsrc": "",
    "config": {
      "ctime": 1699024536,
      "token": "1eeaa620752fb8b981dc7aa6348a8e24",
      "type": "normal"
    },
    "desc": "",
    "extra": "",
    "extraApps": [],
    "meta": {
      "miniapp": {
        "bottomTag": "",
        "bottomTagIcon": "",
        "jumpUrl": "https://api.lyhc.top/bot/a.jpg",
        "preview": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef84cd7189/0",
        "tag": "Tag",
        "tagIcon": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef84cd7189/0",
        "title": "Miniapp card title"
      }
    },
    "prompt": "Display",
    "sourceAd": "",
    "sourceName": "",
    "sourceUrl": "",
    "text": "",
    "ver": "1.0.0.16",
    "view": "miniapp"
  }
```

### 6. Button Card (`/get_btn_card`)

- **Interface Path:** `/get_btn_card`
- **Request Methods:** POST / GET
- **Request Parameters:**

  | Parameter   | Type   | Required | Description         |
  | ----------- | ------ | -------- | ------------------- |
  | prompt      | string | 🔴       | Card display        |
  | title       | string | 🟢       | Button card title   |
  | preview     | string | 🟢       | Preview image URL   |
  | jump        | string | 🟢       | Jump link           |
  | jumpButton  | string | 🔴       | Jump button link    |
  | buttonTitle | string | 🔴       | Button title        |
  | tag         | string | 🔴       | Tag                 |
  | uin         | string | 🟢       | uin                 |
  | skey        | string | 🟢       | skey                |
  | pSkey       | string | 🟢       | p_skey              |

- **Request Body:**

```json
  {
    "prompt": "Display",
    "title": "Button card title",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "jump": "https://api.lyhc.top/bot/a.jpg",
    "jumpButton": "https://www.baidu.com",
    "buttonTitle": "Button text",
    "tag": "Tag",
    "uin": "o2594748568",
    "skey": "@fyexhgBFi",
    "pSkey": "O2NtBlTK6o54-KJMCPer0UyKwWEXjsg0UQ2DFeUxDss_"
  }
```

- **GET Request Example:**

```
https://ark.cwuom.love/get_btn_card?prompt=Display&preview=https://api.lyhc.top/bot/a.jpg&jump=https://api.lyhc.top/bot/a.jpg&jumpButton=https://www.baidu.com&buttonTitle=Button text&tag=Tag&uin=o2594748568&skey=@fyexhgBFi&pSkey=O2NtBlTK6o54-KJMCPer0UyKwWEXjsg0UQ2DFeUxDss_
```

- **Response:**

```json
  {
    "app": "com.tencent.eventshare.lua",
    "prompt": "Display",
    "bizsrc": "tianxuan.business",
    "meta": {
      "eventshare": {
        "button1URL": "https://www.baidu.com",
        "button1disable": false,
        "button1title": "Button text",
        "buttonNum": 1,
        "jumpURL": "https://api.lyhc.top/bot/a.jpg",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "Tag",
        "tagIcon": "",
        "title": "Button card title"
      }
    },
    "config": {
      "autosize": 0,
      "collect": 0,
      "ctime": 1711242525,
      "forward": 1,
      "height": 336,
      "reply": 0,
      "round": 1,
      "token": "cfdf963951e21bc15621be0800152933",
      "type": "normal",
      "width": 263
    },
    "view": "eventshare",
    "ver": "0.0.0.1"
  }
```

# Interface Availability Test Code
```python
import requests

base_url = "https://ark.cwuom.love"

uin = "uin"
p_skey = "pkey"
skey = "skey"
# Test data
test_data = {
    'get_card': {
        "title": "Title",
        "subtitle": "https://api.lyhc.top/bot/a.jpg",
        "prompt": "Display",
        "cover": "https://api.lyhc.top/bot/a.jpg",
    },
    'get_card_news': {
        "desc": "Card description",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "Card tag",
        "tagIcon": "https://api.lyhc.top/bot/a.jpg",
        "title": "Card title",
        "prompt": "Display",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    },
    'get_card_embed': {
        "title": "Embed card title",
        "prompt": "Display",
        "thumbnailUrl": "https://api.lyhc.top/bot/a.jpg",
        "f1": "Field 1,
        "f2": "Field 2",
        "f3": "Field 3",
        "f4": "Field 4",
        "f5": "Field 5"
    },
    'get_btn_card': {
        "prompt": "Display",
        "title": "Button card title",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "jump": "https://api.lyhc.top/bot/a.jpg",
        "jumpButton": "https://www.baidu.com",
        "buttonTitle": "Button text",
        "tag": "Tag",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    },
    'get_miniapp_card': {
        "prompt": "Display",
        "jumpUrl": "https://api.lyhc.top/bot/a.jpg",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "Tag",
        "tagIcon": "https://api.lyhc.top/bot/a.jpg",
        "title": "Miniapp card title",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    }
}

def post_request(endpoint, data):
    """Send a POST request to the specified endpoint"""
    url = f"{base_url}/{endpoint}"
    print("get_url: "+url)
    response = requests.post(url, data=data)
    print(f"Path {endpoint}:")
    print("POST content:", data)
    print("Response: " + response.text)
    print("-" * 50)

for endpoint, data in test_data.items():
    post_request(endpoint, data)
