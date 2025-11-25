< hrml>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>范范解忧</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: "楷体", "SimKai", serif;
            background: #0a0a0a;
            color: #D4AF37;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 30%, rgba(120, 90, 40, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(90, 70, 30, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(110, 80, 35, 0.1) 0%, transparent 50%);
            z-index: -1;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background-color: rgba(10, 10, 10, 0.85);
            border: 3px solid #D4AF37;
            border-radius: 5px;
            padding: 40px 20px;
            box-shadow: 
                0 0 20px rgba(212, 175, 55, 0.2),
                inset 0 0 30px rgba(0, 0, 0, 0.5);
            position: relative;
            z-index: 1;
        }
        
        .seal {
            position: absolute;
            width: 80px;
            height: 80px;
            border: 2px solid #D4AF37;
            border-radius: 5px;
            opacity: 0.3;
            transform: rotate(45deg);
        }
        
        .seal-top-left {
            top: 15px;
            left: 15px;
        }
        
        .seal-top-right {
            top: 15px;
            right: 15px;
        }
        
        .seal-bottom-left {
            bottom: 15px;
            left: 15px;
        }
        
        .seal-bottom-right {
            bottom: 15px;
            right: 15px;
        }
        
        h1 {
            font-size: 3.5rem;
            margin-bottom: 40px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
            letter-spacing: 10px;
            position: relative;
            padding-bottom: 20px;
        }
        
        h1::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 25%;
            width: 50%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #D4AF37, transparent);
        }
        
        .result-container {
            margin: 50px 0;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
        }
        
        .result-container::before {
            content: "「";
            position: absolute;
            left: -30px;
            top: 0;
            font-size: 4rem;
            color: rgba(212, 175, 55, 0.3);
        }
        
        .result-container::after {
            content: "」";
            position: absolute;
            right: -30px;
            bottom: 0;
            font-size: 4rem;
            color: rgba(212, 175, 55, 0.3);
        }
        
        .answer {
            font-size: 3.2rem;
            font-weight: bold;
            color: #D4AF37;
            text-shadow: 
                0 0 10px rgba(212, 175, 55, 0.5),
                2px 2px 4px rgba(0, 0, 0, 0.8);
            margin: 20px 0;
            line-height: 1.3;
            padding: 20px;
            position: relative;
        }
        
        .instructions {
            margin-top: 40px;
            font-size: 1.1rem;
            color: #B8860B;
            line-height: 1.6;
            border-top: 1px solid rgba(212, 175, 55, 0.3);
            padding-top: 20px;
        }
        
        .mystic-symbol {
            position: absolute;
            font-size: 120px;
            color: rgba(212, 175, 55, 0.05);
            z-index: -1;
            user-select: none;
        }
        
        .symbol-1 {
            top: 10%;
            left: 10%;
            transform: rotate(15deg);
        }
        
        .symbol-2 {
            bottom: 10%;
            right: 10%;
            transform: rotate(-15deg);
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
                letter-spacing: 5px;
            }
            
            .answer {
                font-size: 2.2rem;
            }
            
            .container {
                padding: 20px 10px;
            }
            
            .mystic-symbol {
                font-size: 80px;
            }
        }
        
        .fade-in {
            animation: fadeIn 1.5s ease-in-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px) scale(0.95); }
            to { opacity: 1; transform: translateY(0) scale(1); }
        }
    </style>
</head>
<body>
    <div class="mystic-symbol symbol-1">☯</div>
    <div class="mystic-symbol symbol-2">䷀</div>
    
    <div class="seal seal-top-left"></div>
    <div class="seal seal-top-right"></div>
    <div class="seal seal-bottom-left"></div>
    <div class="seal seal-bottom-right"></div>
    
    <div class="container fade-in">
        <h1>范范解忧</h1>
        
        <div class="result-container">
            <div class="answer" id="randomAnswer">奖品正在加载中...</div>
        </div>
        
        <div class="instructions">
            <p>恭喜中奖</p>
            <p>谢谢支持</p>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // 检查是否已经生成了结果
            if (!sessionStorage.getItem('fanfanAnswer')) {
                // 延迟显示结果，增加神秘感
                setTimeout(generateRandomAnswer, 1500);
            } else {
                setTimeout(displayStoredAnswer, 1000);
            }
        });
        
        function generateRandomAnswer() {
            // 定义答案和概率
            const answers = [
                { text: "护符福袋", probability: 60 },
                { text: "免费占卜【3张牌】", probability: 15 },
                { text: "大奖", probability: 5 },
                { text: "水晶福袋", probability: 20 }
            ];
            
            // 生成随机数（0-99）
            const randomValue = Math.floor(Math.random() * 100);
            
            // 根据概率选择答案
            let cumulativeProbability = 0;
            let selectedAnswer = null;
            
            for (const answer of answers) {
                cumulativeProbability += answer.probability;
                if (randomValue < cumulativeProbability) {
                    selectedAnswer = answer;
                    break;
                }
            }
            
            // 存储结果到sessionStorage
            sessionStorage.setItem('fanfanAnswer', JSON.stringify(selectedAnswer));
            
            // 显示结果
            displayAnswer(selectedAnswer);
        }
        
        function displayStoredAnswer() {
            const storedAnswer = JSON.parse(sessionStorage.getItem('fanfanAnswer'));
            displayAnswer(storedAnswer);
        }
        
        function displayAnswer(answer) {
            const answerElement = document.getElementById('randomAnswer');
            
            // 清空内容准备显示新结果
            answerElement.textContent = "";
            answerElement.style.opacity = '0';
            
            // 逐字显示效果
            let index = 0;
            const text = answer.text;
            const timer = setInterval(() => {
                if (index < text.length) {
                    answerElement.textContent += text.charAt(index);
                    index++;
                } else {
                    clearInterval(timer);
                }
            }, 100);
            
            // 淡入效果
            setTimeout(() => {
                answerElement.style.transition = 'opacity 1s ease';
                answerElement.style.opacity = '1';
            }, 500);
        }
    </script>
</body>
</html>
