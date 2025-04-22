# 🤖 DesiaiBot - Plug & Play Chatbot Widget

DesiaiBot is a lightweight, plug-and-play chatbot widget you can embed in any website using just a single `<script>` tag. Ideal for lead generation, support, or user onboarding with minimal setup.

---

## 🚀 Features
- Zero configuration installation
- Mobile number + name collection for personalized chat
- Chat history integration with your backend
- Fully customizable (theme, title, position)
- Works on any HTML, JS, or React site

---

## 📦 Integration via CDN

### 1. Add Script to HTML
Paste this before your closing `</body>` tag:

```html
<script src="https://cdn.jsdelivr.net/gh/darksmogai/DesiaiBot@v1.0.0/DesiaiBot.js"></script>
<script>
  initDesiaiBot({
    userId: "user@domain.com",
    theme: "light", // or "dark"
    title: "DesiaiBot",
    position: "bottom-right", // or "bottom-left"
    backendUrl: "https://yourapi.com"
  });
</script>
```

---

## 💬 Chat Flow
1. Click on the floating 💬 icon
2. Bot asks for 10-digit mobile number
3. Then asks for user name
4. Begins chatting and saves messages via your backend

---

## 🔌 Backend API Requirements

### `/api/chat/history`
```http
POST /api/chat/history
Content-Type: application/json
{
  "mobile": "1234567890",
  "userId": "user@domain.com"
}
```
**Response:**
```json
[
  { "sender": "bot", "message": "Hi there!" },
  { "sender": "user", "message": "Hello!" }
]
```

### `/api/chat/send`
```http
POST /api/chat/send
Content-Type: application/json
{
  "mobile": "1234567890",
  "userid": "user@domain.com",
  "text": "Hello",
  "sender": "user",
  "sendername": "John"
}
```
**Response:**
```json
{
  "message": "Thanks for your message!"
}
```

---

## ⚙️ Configuration Options
| Option       | Type     | Description                            |
|--------------|----------|----------------------------------------|
| `userId`     | string   | Required for backend tracking          |
| `theme`      | string   | `light` or `dark`                      |
| `title`      | string   | Custom title in the chat header        |
| `position`   | string   | `bottom-right` or `bottom-left`        |
| `backendUrl` | string   | Base URL of your backend server        |

---

## 📸 Screenshots
Add screenshots or a GIF demo to showcase how it looks.

---

## 📝 License
MIT License

---

## ✨ Made by [DarkSmogAI](https://github.com/darksmogai)

