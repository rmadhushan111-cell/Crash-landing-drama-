# Crash-landing-drama-
අපේ group එකට private drama voice website එකක්
<!DOCTYPE html><html lang="si">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Drama Voice Room</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(180deg, #020617, #0f172a);
      color: #fff;
    }
    .app {
      max-width: 420px;
      margin: auto;
      padding: 16px;
    }
    h2 {
      text-align: center;
      margin-bottom: 4px;
    }
    .subtitle {
      text-align: center;
      font-size: 14px;
      opacity: 0.8;
      margin-bottom: 16px;
    }
    .room {
      background: #020617;
      border-radius: 16px;
      padding: 16px;
      box-shadow: 0 0 20px rgba(0,0,0,0.5);
      margin-bottom: 16px;
    }
    .room p { margin: 6px 0; }
    button {
      width: 100%;
      padding: 14px;
      margin-top: 10px;
      border: none;
      border-radius: 14px;
      background: #2563eb;
      color: white;
      font-size: 16px;
    }
    button.mute { background: #dc2626; }
    .chat {
      background: #020617;
      border-radius: 14px;
      padding: 10px;
      height: 140px;
      overflow-y: auto;
      font-size: 14px;
    }
    input {
      width: 100%;
      padding: 12px;
      border-radius: 12px;
      border: none;
      margin-top: 8px;
      font-size: 14px;
    }
    .footer {
      text-align: center;
      font-size: 12px;
      opacity: 0.6;
      margin-top: 12px;
    }
  </style>
</head>
<body>
  <div class="app">
    <h2>🎭 Drama Voice Room</h2>
    <div class="subtitle">Private Group – Web App Demo</div><div class="room">
  <p><b>Room:</b> Night Drama Talk</p>
  <p><b>Moderator:</b> Admin</p>
  <button onclick="joinRoom()">Join Voice Room</button>
  <button class="mute" onclick="toggleMute()">Mute / Unmute</button>
</div>

<div class="chat" id="chatBox"></div>
<input type="text" id="msg" placeholder="Message type කරන්න..." />
<button onclick="sendMsg()">Send</button>

<div class="footer">Demo only – Real voice streaming not connected</div>

  </div>  <script>
    let joined = false;
    let muted = false;

    function joinRoom() {
      joined = true;
      log("ඔයා room එකට join වුණා 🎤");
    }

    function toggleMute() {
      if (!joined) {
        alert("මුලින් room එකට join වෙන්න");
        return;
      }
      muted = !muted;
      log(muted ? "Mic mute වුණා 🔇" : "Mic unmute වුණා 🔊");
    }

    function sendMsg() {
      const input = document.getElementById('msg');
      if (!input.value) return;
      log("You: " + input.value);
      input.value = "";
    }

    function log(text) {
      const box = document.getElementById('chatBox');
      box.innerHTML += `<div>${text}</div>`;
      box.scrollTop = box.scrollHeight;
    }
  </script></body>
</html>
