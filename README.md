# Chat-Application
This is a Chat Application website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Chat Application</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }
    #chat-box {
      width: 300px;
      height: 400px;
      border: 1px solid #ccc;
      overflow-y: scroll;
      padding: 10px;
    }
    #message-input {
      width: 250px;
    }
    #send-button {
      width: 50px;
    }
  </style>
</head>
<body>
  <div id="chat-box"></div>
  <div>
    <input type="text" id="message-input" placeholder="Type a message...">
    <button id="send-button">Send</button>
  </div>

  <script>
    const chatBox = document.getElementById('chat-box');
    const messageInput = document.getElementById('message-input');
    const sendButton = document.getElementById('send-button');

    sendButton.addEventListener('click', () => {
      const message = messageInput.value;
      if (message.trim() !== '') {
        appendMessage('You', message);
        messageInput.value = '';
      }
    });

    function appendMessage(sender, message) {
      const messageElement = document.createElement('div');
      messageElement.innerHTML = `<strong>${sender}:</strong> ${message}`;
      chatBox.appendChild(messageElement);
      chatBox.scrollTop = chatBox.scrollHeight;
    }
  </script>
</body>
</html>
