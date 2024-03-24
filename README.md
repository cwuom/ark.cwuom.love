<h1 align="center">ARK签名接口文档</h1>
<div align="center">

<p align="center">
    <h3>通过此API，你可以生成并签名市面上大多数的卡片，适用于QQ</h3>
    <p align="center">
        <a href="https://t.me/cwuoms_group">
<img alt="JoinTelegramGroup" src="https://img.shields.io/badge/Telegram-Group-blue" />
</a>
<p>
    
  **&gt; 简体中文 &lt;** | [English](README_EN.md)
</div>

# ARK消息生成接口文档
## 接口信息
### 本文档提供了ARK消息生成接口的详细说明，支持通过POST和GET方法请求。
- 接口地址: `https://ark.cwuom.love`
- 测试中，现全面开放，不保证长期可用性，后续也许会添加接口鉴权。

## 调用说明
### 1. 大图ARK卡片 (`/get_card`)

- **接口路径:** `/get_card`
- **请求方法:** POST / GET
- **请求参数:**

  | 参数名   | 类型   | 是否必须 | 描述         |
  | -------- | ------ | -------- | ------------ |
  | title    | string | 🟥       | 卡片标题     |
  | subtitle | string | 🟥       | 卡片副标题   |
  | prompt   | string | 🟥       | 卡片外显     |
  | cover    | string | 🟢       | 预览图片URL  |

- **Request Body:**

 ```json
  {
    "title": "标题",
    "subtitle": "https://api.lyhc.top/bot/a.jpg",
    "prompt": "外显",
    "cover": "https://api.lyhc.top/bot/a.jpg"
  }
 ```

- **GET请求示例:**

```
https://ark.cwuom.love/get_card?title=标题&subtitle=副标题&prompt=卡片外显&cover=https://api.lyhc.top/bot/a.jpg
```

- **响应:**

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
        "title": "标题"
      }
    },
    "prompt": "外显",
    "ver": "1.0.0.14",
    "view": "index"
  }
 ```

### 2. 分享类型ARK卡片 (`/get_card_news`)

- **接口路径:** `/get_card_news`
- **请求方法:** POST / GET
- **请求参数:**

  | 参数名   | 类型   | 是否必须 | 描述         |
  | -------- | ------ | -------- | ------------ |
  | desc     | string | 🟥       | 卡片描述     |
  | preview  | string | 🟢       | 预览图URL    |
  | tag      | string | 🟥       | 标签文本     |
  | tagIcon  | string | 🟢       | 标签图标URL  |
  | title    | string | 🟥       | 卡片标题     |
  | prompt   | string | 🟥       | 卡片外显     |
  | uin      | string | 🟢       | uin     |
  | skey     | string | 🟢       | skey     |
  | pSkey    | string | 🟢       | p_skey |

- **Request Body:**

 ```json
  {
    "desc": "卡片描述",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "tag": "卡片标签",
    "tagIcon": "https://api.lyhc.top/bot/a.jpg",
    "title": "卡片标题",
    "prompt": "外显",
    "uin": "o2594748568",
    "skey": "@rbVjLgTMH",
    "pSkey": "BiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyIE3II3M_"
  }
 ```

- **GET请求示例:**

```
https://ark.cwuom.love/get_card_news?desc=卡片描述&preview=https://api.lyhc.top/bot/a.jpg&tag=卡片标签&tagIcon=https://api.lyhc.top/bot/a.jpg&title=卡片标题&prompt=外显&uin=o2594748568&skey=@rbVjLgTMH&pSkey=BiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyIE3II3M_
```

- **响应:**

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
        "desc": "卡片描述",
        "jumpUrl": "",
        "preview": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef846c2520/0",
        "tag": "卡片标签",
        "tagIcon": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef846c2520/0",
        "title": "卡片标题"
      }
    },
    "prompt": "外显",
    "view": "news"
  }
 ```

### 3. Embed卡片 (`/get_card_embed`)

- **接口路径:** `/get_card_embed`
- **请求方法:** POST / GET
- **请求参数:**

  | 参数名       | 类型   | 是否必须 | 描述         |
  | ------------ | ------ | -------- | ------------ |
  | title        | string | 🟥       | 卡片标题     |
  | prompt       | string | 🟥       | 卡片外显     |
  | thumbnailUrl | string | 🟥       | 缩略图URL    |
  | f1           | string | 🟥       | 字段1内容    |
  | f2           | string | 🟥       | 字段2内容    |
  | f3           | string | 🟥       | 字段3内容    |
  | f4           | string | 🟥       | 字段4内容    |
  | f5           | string | 🟥       | 字段5内容    |

- **Request Body:**

  ```json
  {
    "title": "embed卡片标题",
    "prompt": "外显",
    "thumbnailUrl": "https://api.lyhc.top/bot/a.jpg",
    "f1": "字段1",
    "f2": "字段2",
    "f3": "字段3",
    "f4": "字段4",
    "f5": "字段5"
  }
  ```

- **GET请求示例:**

```
https://ark.cwuom.love/get_card_embed?title=embed卡片标题&prompt=外显&thumbnailUrl=https://api.lyhc.top/bot/a.jpg&f1=字段1&f2=字段2&f3=字段3&f4=字段4&f5=字段5
```

- **响应:**

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
          {"name": "字段1"},
          {"name": "字段2"},
          {"name": "字段3"},
          {"name": "字段4"},
          {"name": "字段5"}
        ],
        "thumbnail": {"url": "https://api.lyhc.top/bot/a.jpg"},
        "title": "embed卡片标题"
      }
    },
    "prompt": "外显",
    "ver": "1.0.0.9",
    "view": "index"
  }
  ```

### 5. 小程序ARK卡片 (`/get_miniapp_card`)

- **接口路径:** `/get_miniapp_card`
- **请求方法:** POST / GET
- **请求参数:**

  | 参数名   | 类型   | 是否必须 | 描述             |
  | -------- | ------ | -------- | ---------------- |
  | prompt   | string | 🟥       | 卡片外显         |
  | jumpUrl  | string | 🟥       | 跳转链接         |
  | preview  | string | 🟢       | 预览图URL        |
  | tag      | string | 🟥       | 标签             |
  | tagIcon  | string | 🟢       | 标签图标URL      |
  | title    | string | 🟥       | 小程序卡片标题   |
  | uin      | string | 🟢       | uin         |
  | skey     | string | 🟢       | skey         |
  | pSkey    | string | 🟢       | p_skey     |

- **Request Body:**

  ```json
  {
    "prompt": "外显",
    "jumpUrl": "https://api.lyhc.top/bot/a.jpg",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "tag": "标签",
    "tagIcon": "https://api.lyhc.top/bot/a.jpg",
    "title": "小程序卡片标题",
    "uin": "o2594748568",
    "skey": "@rbHjPfTMH",
    "pSkey": "rfHjlfTMBiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3L_"
  }
  ```

- **GET请求示例:**

```
https://ark.cwuom.love/get_miniapp_card?prompt=外显&jumpUrl=https://api.lyhc.top/bot/a.jpg&preview=https://api.lyhc.top/bot/a.jpg&tag=标签&tagIcon=https://api.lyhc.top/bot/a.jpg&title=小程序卡片标题&uin=o2594748568&skey=@rbHjPfTMH&pSkey=rfHjlfTMBiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3L_
```

- **响应:**

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
        "tag": "标签",
        "tagIcon": "http://p.qlogo.cn/homework/0/hw_h_3sveyc22j10k4wg65fef84cd7189/0",
        "title": "小程序卡片标题"
      }
    },
    "prompt": "外显",
    "sourceAd": "",
    "sourceName": "",
    "sourceUrl": "",
    "text": "",
    "ver": "1.0.0.16",
    "view": "miniapp"
  }
  ```

  
- **GET请求示例:**
```
https://ark.cwuom.love/get_card_embed?title=embed卡片标题&prompt=外显&thumbnailUrl=https://api.lyhc.top/bot/a.jpg&f1=字段1&f2=字段2&f3=字段3&f4=字段4&f5=字段5](https://ark.cwuom.love/get_btn_card?prompt=%E5%95%8A%E5%95%8A&title=%E5%93%88%E5%93%88%E5%93%88&preview=https://tianquan.gtimg.cn/chatBg/item/53693/newPreview2.png&jump=https://www.baidu.com&jumpButton=https://tianquan.gtimg.cn/chatBg/item/53693/newPreview2.png&buttonTitle=%E6%8C%89%E9%92%AE&%20tag=&uin=o2594748568&skey=@rbHjPfTMH&pSkey=rfHjlfTMBiZak42zMo9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3L_)https://ark.cwuom.love/get_btn_card?prompt=%E5%95%8A%E5%95%8A&title=%E5%93%88%E5%93%88%E5%93%88&preview=https://tianquan.gtimg.cn/chatBg/item/53693/newPreview2.png&jump=https://www.baidu.com&jumpButton=https://tianquan.gtimg.cn/chatBg/item/53693/newPreview2.png&buttonTitle=%E6%8C%89%E9%92%AE&%20tag=&uin=o2594748568&skey=@rbVlPgTWH&pSkey=BiZakd2zMp9y2w8Ykhy5Yl8NNgngL09jx6AyiE3IL3M_
```

### 6. 按钮卡片 (`/get_btn_card`)

- **接口路径:** `/get_btn_card`
- **请求方法:** POST / GET
- **请求参数:**

  | 参数名      | 类型   | 是否必须 | 描述             |
  | ----------- | ------ | -------- | ---------------- |
  | prompt      | string | 🟥       | 卡片外显         |
  | title       | string | 🟢       | 按钮卡片标题     |
  | preview     | string | 🟢       | 预览图URL        |
  | jump        | string | 🟢       | 跳转链接         |
  | jumpButton  | string | 🟥       | 跳转按钮链接     |
  | buttonTitle | string | 🟥       | 按钮标题         |
  | tag         | string | 🟥       | 标签             |
  | uin         | string | 🟢       | uin              |
  | skey        | string | 🟢       | skey             |
  | pSkey       | string | 🟢       | p_skey           |

- **Request Body:**

  ```json
  {
    "prompt": "",
    "title": "aa",
    "preview": "https://api.lyhc.top/bot/a.jpg",
    "jump": "https://api.lyhc.top/bot/a.jpg",
    "jumpButton": "",
    "buttonTitle": "",
    "tag": "",
    "uin": "o2594748568",
    "skey": "@fyexhgBFi",
    "pSkey": "O2NtBlTK6o54-KJMCPer0UyKwWEXjsg0UQ2DFeUxDss_"
  }
  ```


- **GET请求示例:**
```
https://ark.cwuom.love/get_btn_card?prompt=&preview&=jump=&jumpButton=&buttonTitle=tag=&uin=&skey=&pSkey=
```

- **响应:**

  ```json
  {
    "app": "com.tencent.eventshare.lua",
    "prompt": "",
    "bizsrc": "tianxuan.business",
    "meta": {
      "eventshare": {
        "button1URL": "",
        "button1disable": false,
        "button1title": "",
        "buttonNum": 1,
        "jumpURL": "https://api.lyhc.top/bot/a.jpg",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "",
        "tagIcon": "",
        "title": "aa"
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


# 接口测试代码
```python
import requests

base_url = "https://ark.cwuom.love"

uin = "uin"
p_skey = "pkey"
skey = "skey"
# 测试数据
test_data = {
    'get_card': {
        "title": "标题",
        "subtitle": "https://api.lyhc.top/bot/a.jpg",
        "prompt": "外显",
        "cover": "https://api.lyhc.top/bot/a.jpg",
    },
    'get_card_news': {
        "desc": "卡片描述",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "卡片标签",
        "tagIcon": "https://api.lyhc.top/bot/a.jpg",
        "title": "卡片标题",
        "prompt": "外显",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    },
    'get_card_embed': {
        "title": "embed卡片标题",
        "prompt": "外显",
        "thumbnailUrl": "https://api.lyhc.top/bot/a.jpg",
        "f1": "字段1",
        "f2": "字段2",
        "f3": "字段3",
        "f4": "字段4",
        "f5": "字段5"
    },
    'get_btn_card': {
        "prompt": "外显",
        "title": "按钮卡片标题",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "jump": "https://api.lyhc.top/bot/a.jpg",
        "jumpButton": "https://www.baidu.com",
        "buttonTitle": "按钮文字",
        "tag": "标签",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    },
    'get_miniapp_card': {
        "prompt": "外显",
        "jumpUrl": "https://api.lyhc.top/bot/a.jpg",
        "preview": "https://api.lyhc.top/bot/a.jpg",
        "tag": "标签",
        "tagIcon": "https://api.lyhc.top/bot/a.jpg",
        "title": "小程序卡片标题",
        "uin": uin,
        "skey": skey,
        "pSkey": p_skey
    }
}


def post_request(endpoint, data):
    """发送 POST 请求到指定的终端"""
    url = f"{base_url}/{endpoint}"
    print("get_url: "+url)
    response = requests.post(url, data=data)
    print(f"路径 {endpoint}:")
    print("post内容:", data)
    print("返回: " + response.text)
    print("-" * 50)

for endpoint, data in test_data.items():
    post_request(endpoint, data)

```
