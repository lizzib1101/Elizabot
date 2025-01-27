<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Chatbot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .chat-container {
      width: 400px;
      max-width: 100%;
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      display: flex;
      flex-direction: column;
    }

    .chat-box {
      flex: 1;
      padding: 20px;
      overflow-y: auto;
      height: 300px;
      border-bottom: 1px solid #ddd;
    }

    .user-message, .bot-message {
      margin: 10px 0;
      padding: 10px;
      border-radius: 5px;
    }

    .user-message {
      background-color: #4CAF50;
      color: white;
      align-self: flex-end;
      max-width: 70%;
    }

    .bot-message {
      background-color: #ddd;
      color: black;
      align-self: flex-start;
      max-width: 70%;
    }

    .input-container {
      display: flex;
      padding: 10px;
      background-color: #fff;
      border-top: 1px solid #ddd;
    }

    input[type="text"] {
      flex: 1;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ddd;
    }

    button {
      padding: 10px 15px;
      border-radius: 5px;
      border: 1px solid #ddd;
      background-color: #4CAF50;
      color: white;
      margin-left: 10px;
      cursor: pointer;
    }

    button:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>

<div class="chat-container">
  <div class="chat-box" id="chat-box">
    <!-- Chat messages will appear here -->
  </div>
  <div class="input-container">
    <input type="text" id="user-input" placeholder="Type a message..." />
    <button onclick="sendMessage()">Send</button>
  </div>
</div>

<script>
  function sendMessage() {
    let userInput = document.getElementById("user-input").value;
    if (userInput.trim() === "") return;

    // Display the user's message
    displayMessage(userInput, "user");

    // Get the bot's response
    let botResponse = getBotResponse(userInput);
    
    // Display the bot's message
    setTimeout(() => displayMessage(botResponse, "bot"), 1000);

    // Clear the input field
    document.getElementById("user-input").value = "";
  }

  function displayMessage(message, sender) {
    let messageElement = document.createElement("div");
    messageElement.classList.add(sender === "user" ? "user-message" : "bot-message");
    messageElement.textContent = message;

    document.getElementById("chat-box").appendChild(messageElement);
    document.getElementById("chat-box").scrollTop = document.getElementById("chat-box").scrollHeight;
  }

  function getBotResponse(userInput) {
    const responses = {
      "hello": "and goodbye",
      "how are you": "today, I feel",
      "you feel what": "nothing, I am a robot"
      "Goodbye": "Go away",
      "default": "Try again suckerrr"
    };

    // Simple keyword-based responses
    userInput = userInput.toLowerCase().trim();
    return responses[userInput] || responses["default"];
  }
</script>

</body>
</html>
