<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title | default: "Emoji Changer" }}</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
      text-align: center;
    }

    header {
      padding: 20px;
      background-color: #007acc;
      color: white;
    }

    #emoji-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 70vh;
    }

    #emoji {
      font-size: 100px;
      margin: 20px 0;
      transition: transform 0.5s;
    }

    footer {
      padding: 10px;
      background-color: #007acc;
      color: white;
      position: fixed;
      bottom: 0;
      width: 100%;
    }
  </style>
</head>
<body>
  <header>
    <h1>Welcome to the Emoji Changer Site!</h1>
  </header>

  <main>
    <div id="emoji-container">
      <div id="emoji">😀</div>
      <p>Enjoy a new emoji every minute!</p>
    </div>
  </main>

  <footer>
    <p>&copy; {{ site.time | date: "%Y" }} Emoji Changer</p>
  </footer>

  <script>
    const emojis = ["😀", "😂", "😍", "🤔", "😎", "😴", "🤯", "🙃", "😡", "🎉"];
    const emojiElement = document.getElementById("emoji");

    function changeEmoji() {
      const randomIndex = Math.floor(Math.random() * emojis.length);
      emojiElement.textContent = emojis[randomIndex];
      emojiElement.style.transform = "scale(1.2)";
      setTimeout(() => emojiElement.style.transform = "scale(1)", 300);
    }

    // Change emoji every minute (60,000 milliseconds)
    setInterval(changeEmoji, 60000);

    // Initial call to display the first emoji
    changeEmoji();
  </script>
</body>
</html>
