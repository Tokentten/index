<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>Share Flex</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://static.line-scdn.net/liff/edge/2/sdk.js"></script>
</head>

<body style="font-family:sans-serif;text-align:center;padding:30px">

  <h2>แชร์โปรโมชั่น</h2>
  <button onclick="shareFlex()" style="
    background:#00C300;
    color:#fff;
    border:none;
    padding:15px 25px;
    font-size:18px;
    border-radius:10px;
  ">
    แชร์ให้เพื่อน
  </button>

<script>
async function shareFlex() {
  await liff.init({ liffId: "2008740636-oTHcHAmb" });

  await liff.shareTargetPicker([
    {
      type: "flex",
      altText: "แจกฟรี",
      contents: FLEX_JSON
    }
  ]);
}

// Flex JSON
const FLEX_JSON = {
  "type": "bubble",
  "hero": {
    "type": "image",
    "url": "https://lh3.googleusercontent.com/d/1DZBc3t9TDhPrk-z31neQ_-PRwC6MrLG6",
    "size": "full",
    "aspectRatio": "1:1",
    "aspectMode": "cover",
    "action": {
      "type": "uri",
      "uri": "https://auto.aoxbet99.ltd/"
    }
  },
  "body": {
    "type": "box",
    "layout": "vertical",
    "contents": [
      {
        "type": "text",
        "text": "แจกฟรี",
        "weight": "bold",
        "size": "4xl",
        "align": "center"
      }
    ]
  },
  "footer": {
    "type": "box",
    "layout": "vertical",
    "spacing": "sm",
    "contents": [
      {
        "type": "button",
        "style": "primary",
        "height": "sm",
        "color": "#6633CC",
        "action": {
          "type": "uri",
          "label": "รับฟรี",
          "uri": "https://auto.aoxbet99.ltd/"
        }
      },
      {
        "type": "button",
        "style": "primary",
        "height": "sm",
        "color": "#00C300",
        "action": {
          "type": "uri",
          "label": "สมัคร",
          "uri": "https://auto.aoxbet99.ltd/"
        }
      }
    ]
  }
};
</script>

</body>
</html>
