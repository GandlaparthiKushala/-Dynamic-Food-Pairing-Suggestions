# Dynamic-Food-Pairing-Suggestions
An application that provides real-time food pairing suggestions based on current ingredients users have. As users add or remove ingredients, the app dynamically suggests new recipes or pairings.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Food Pairing Suggestion and Random Tips</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('https://cdn.georgeinstitute.org/sites/default/files/styles/width1920_fallback/public/2020-10/world-food-day-2020.png'); /* Background image URL */
            background-size: cover;
            background-position: center;
            color: #333;
            margin: 0;
            padding: 0;
            text-align: center;
            height: 100vh; /* Ensure the background covers the entire viewport height */
        }
        .container {
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.8); /* Semi-transparent background for readability */
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        input[type="text"], button {
            padding: 10px;
            margin: 10px;
            border-radius: 4px;
            border: 1px solid #ddd;
            font-size: 16px;
        }
        button {
            background-color: #4CAF50;
            color: #fff;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            font-size: 18px;
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Food Pairing Suggestion</h1>
        <p>Type in a food item to get a suggestion:</p>
        <input type="text" id="foodInput" placeholder="Enter a food item">
        <button onclick="suggestPairing()">Get Suggestion</button>
        <div id="result" class="result"></div>
    </div>

    <div class="container">
        <h1>Random Tips</h1>
        <button onclick="showRandomTip()">Show a Random Tip</button>
        <div id="tip" class="result"></div>
    </div>

    <script>
        function suggestPairing() {
            const input = document.getElementById('foodInput').value.trim().toLowerCase();
            if (input) {
                window.location.href = `suggestion.html?food=${encodeURIComponent(input)}`;
            } else {
                document.getElementById('result').innerText = 'Please enter a food item.';
            }
        }

        function showRandomTip() {
            const tips = [
                'Stay hydrated! Drink at least 8 glasses of water a day.',
                'Incorporate more fruits and vegetables into your diet for better health.',
                'Take breaks during work to stretch and avoid sitting for long periods.',
                'Practice mindfulness or meditation to reduce stress.',
                'Exercise regularly to keep your body and mind healthy.',
                'Ensure you get enough sleep each night for optimal functioning.',
                'Wash your hands frequently to prevent the spread of germs.',
                'Limit your intake of sugary drinks and snacks.',
                'Stay connected with friends and family for emotional support.',
                'Plan your meals in advance to maintain a balanced diet.'
            ];

            const randomIndex = Math.floor(Math.random() * tips.length);
            const randomTip = tips[randomIndex];

            document.getElementById('tip').innerText = randomTip;
        }
    </script>
</body>
</html>

