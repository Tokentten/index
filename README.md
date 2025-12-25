<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>Share Flex (LIFF Demo)</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://static.line-scdn.net/liff/edge/2/sdk.js"></script>
</head>

<body style="font-family:sans-serif;text-align:center;padding:30px">

  <h2>แชร์โปรโมชั่น (LIFF Demo)</h2>
  <p>หมายเหตุ: LIFF_ID ถูกตั้งค่าแล้ว และ imageUrl ชี้ไปยังภาพที่คุณให้มา หากต้องการเก็บไฟล์ใน repo ให้ส่งรูปโดยตรงเพื่ออัปโหลด</p>

  <button id="shareBtn" style="
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
const LIFF_ID = "2008740636-oTHcHAmb"; // LIFF ID ของคุณ
const imageUrl = "https://i.postimg.cc/RhmkBLyy/kherd-tfr-100-2.jpg"; // ใช้ URL ที่คุณให้มา

// Flex JSON
const FLEX_JSON = {
  "type": "bubble",
  "hero": {
    "type": "image",
    "url": imageUrl,
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

async function initLiff() {
  try {
    await liff.init({ liffId: LIFF_ID });
    console.log('LIFF initialized');

    if (!liff.isInClient()) {
      console.warn('Not running inside LINE app — shareTargetPicker may not work outside LINE in-app browser.');
    }

    if (!liff.isApiAvailable('shareTargetPicker')) {
      console.warn('shareTargetPicker API is not available in this LIFF SDK/environment.');
    }
  } catch (err) {
    console.error('LIFF init failed:', err);
    alert('LIFF initialization failed: ' + (err.message || err));
  }
}

async function shareFlex() {
  try {
    if (!liff.isApiAvailable('shareTargetPicker')) {
      alert('shareTargetPicker ไม่สามารถใช้ได้ในสภาพแวดล้อมนี้');
      return;
    }

    await liff.shareTargetPicker([
      {
        type: "flex",
        altText: "แจกฟรี",
        contents: FLEX_JSON
      }
    ]);

    alert('แชร์คำร้องขอเรียบร้อย (ถ้าคุณเลือกผู้รับแล้ว)');
  } catch (err) {
    console.error('shareTargetPicker error:', err);
    alert('เกิดข้อผิดพลาดในการแชร์: ' + (err.message || err));
  }
}

document.getElementById('shareBtn').addEventListener('click', shareFlex);

// เรียก init ตอนโหลดหน้า
initLiff();
</script>

</body>
</html>
