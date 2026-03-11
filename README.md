<div align="center">
  <img width="256" height="256" alt="image" src="https://github.com/user-attachments/assets/ebcb0e02-7261-4fc4-9590-27be441ec591" />
</div>
<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-2.3+-green.svg)
![Neonize](https://img.shields.io/badge/Neonize-0.3.11-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)

**Complete WhatsApp REST API with comprehensive media support**

*Create QrCode • Send text, images, documents, audio, video & stickers programmatically*

---

 <a href="https://github.com/ariessetiyawan/neonize-wa-api?tab=readme-ov-file#-abaut">About</a> • <a href="https://github.com/ariessetiyawan/neonize-wa-api?tab=readme-ov-file#-examples">Examples</a> • <a href="https://github.com/ariessetiyawan/neonize-wa-api?tab=readme-ov-file#-documentation">Documentation</a> • <a href="https://github.com/ariessetiyawan/neonize-wa-api?tab=readme-ov-file#-source">Source</a>

</div>

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/1f859e8b-1057-452d-b522-44e81a86a2b9" />

# 🧩 Neonize-wa-api
✅ Creating a Unofficial WhatsApp API Using Python with Neonize Library.

✅ Complete WhatsApp REST API with comprehensive media support.

✅ Single session.


## 📖 Documentation

### API Endpoints

| Endpoint | Method | Description | Media Support |
|----------|--------|-------------|---------------|
| `GET /` | GET | API health & info | - |
| `GET /api/qrcode/<type>` | GET | Bot QRCode Created | Text,Base64,Images|
| `GET /api/status` | GET | Bot connection status | - |
| `POST /api/send-message` | POST | Send text message | Text |
| `POST /api/send-image` | POST | Send image with caption | Images |
| `POST /api/send-document` | POST | Send document with caption | Documents |
| `POST /api/send-audio` | POST | Send audio file | Audio |
| `POST /api/send-video` | POST | Send video with caption | Video |
| `POST /api/send-sticker` | POST | Send WebP sticker | Stickers |

### Supported File Types

| Media Type | Extensions | Max Size | Caption |
|------------|------------|----------|---------|
| **Images** | jpg, jpeg, png, gif, webp | 16MB | ✅ |
| **Documents** | pdf, doc, docx, xls, xlsx, ppt, pptx, txt, zip, rar, 7z | 32MB | ✅ |
| **Audio** | mp3, wav, ogg, m4a, aac, flac | 16MB | ❌ |
| **Video** | mp4, avi, mov, mkv, webm, 3gp, flv | 64MB | ✅ |
| **Stickers** | webp | 1MB | ❌ |

---

## 🧪 Examples

### Send Text Message

```bash
curl -X POST http://localhost:5000/api/send-message \
  -H "Content-Type: application/json" \
  -d '{
    "phone": "6281234567890",
    "message": "Hello from WhatsApp API! 🚀"
  }'
```

### Send Image with Caption

```bash
curl -X POST http://localhost:5000/api/send-image \
  -F "phone=6281234567890" \
  -F "caption=📸 Beautiful sunset!" \
  -F "file=@image.jpg"
```

### Send Document

```bash
curl -X POST http://localhost:5000/api/send-document \
  -F "phone=6281234567890" \
  -F "caption=📄 Important report" \
  -F "file=@report.pdf"
```

### Send Audio

```bash
curl -X POST http://localhost:5000/api/send-audio \
  -F "phone=6281234567890" \
  -F "file=@voice_message.mp3"
```

### Send Video

```bash
curl -X POST http://localhost:5000/api/send-video \
  -F "phone=6281234567890" \
  -F "caption=🎬 Demo video" \
  -F "file=@demo.mp4"
```

### Python Example

```python
import requests

# Send text message
response = requests.post('http://localhost:5000/api/send-message', json={
    "phone": "6281234567890",
    "message": "Hello from Python! 🐍"
})

print(response.json())

# Send image
with open('image.jpg', 'rb') as f:
    response = requests.post('http://localhost:5000/api/send-image', 
        files={'file': f},
        data={'phone': '6281234567890', 'caption': '📸 Python image'}
    )
    
print(response.json())
```

### JavaScript Example

```javascript
// Send text message
const response = await fetch('http://localhost:5000/api/send-message', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    phone: '6281234567890',
    message: 'Hello from JavaScript! 🌟'
  })
});

const result = await response.json();
console.log(result);

// Send image
const formData = new FormData();
formData.append('phone', '6281234567890');
formData.append('caption', '📸 JavaScript image');
formData.append('file', fileInput.files[0]);

const imageResponse = await fetch('http://localhost:5000/api/send-image', {
  method: 'POST',
  body: formData
});

console.log(await imageResponse.json());
```

---

## 🌐 Response Format

### Success Response
```json
{
  "status": "success",
  "message": "Message sent successfully",
  "data": {
    "phone": "6281234567890",
    "message": "Hello World!",
    "type": "text",
    "timestamp": "2025-08-15 17:38:34.475734"
  }
}
```

### Error Response
```json
{
  "status": "error",
  "message": "Bot not connected"
}
```

---

## 📎 Source
1. https://github.com/krypton-byte/neonize
2. https://github.com/classyid/neonize-whatsapp-api
