<!DOCTYPE html>
<html>
<head>
    <title>我的随机答案生成器</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
        }
        .answer {
            font-size: 3em;
            font-weight: bold;
            margin: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        button {
            padding: 15px 30px;
            font-size: 1.2em;
            border: none;
            border-radius: 10px;
            background-color: #fff;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="answer" id="result">请点击按钮</div>
    <button onclick="generateAnswer()">获取随机答案</button>

    <script>
        // 在这里修改你的答案列表！
        const answers = [
            "是",
            "否",
            "毫无疑问",
            "想得美",
            "可能性很大",
            "最好不要",
            "相信直觉",
            "这还用问？"
        ];

        function generateAnswer() {
            const randomIndex = Math.floor(Math.random() * answers.length);
            const selectedAnswer = answers[randomIndex];
            document.getElementById('result').textContent = selectedAnswer;
        }
    </script>
</body>
</html>
