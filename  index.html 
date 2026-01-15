<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>范范占卜</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: "SimSun", "宋体", "STKaiti", "华文楷体", serif;
            background-color: #1a0f0a;
            background-image: 
                radial-gradient(circle at 20% 30%, rgba(139, 69, 19, 0.2) 0%, transparent 20%),
                radial-gradient(circle at 80% 70%, rgba(101, 67, 33, 0.2) 0%, transparent 20%);
            color: #e6d5b8;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            position: relative;
        }
        
        .container {
            max-width: 1000px;
            width: 100%;
            background-color: rgba(26, 15, 10, 0.9);
            border: 5px double #c19a6b;
            border-radius: 10px;
            padding: 40px 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.7);
            position: relative;
            z-index: 1;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            position: relative;
        }
        
        .header h1 {
            font-size: 4rem;
            color: #d4af37;
            text-shadow: 3px 3px 5px rgba(0, 0, 0, 0.8);
            letter-spacing: 8px;
            margin-bottom: 15px;
        }
        
        .subtitle {
            font-size: 1.8rem;
            color: #e6d5b8;
            font-style: italic;
            margin-top: 10px;
        }
        
        .gua-container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
            margin: 40px 0;
        }
        
        .gua-card {
            background-color: rgba(40, 25, 15, 0.8);
            border: 3px solid #c19a6b;
            border-radius: 15px;
            padding: 30px 20px;
            text-align: center;
            min-height: 400px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .gua-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(193, 154, 107, 0.3);
        }
        
        .gua-symbol {
            font-size: 6rem;
            color: #d4af37;
            margin: 20px 0;
            text-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
        }
        
        .gua-name {
            font-size: 2.8rem;
            color: #f2c94c;
            margin: 15px 0;
            letter-spacing: 2px;
        }
        
        .gua-number {
            font-size: 1.5rem;
            color: #c19a6b;
            margin-bottom: 10px;
        }
        
        .gua-desc {
            font-size: 1.3rem;
            color: #e6d5b8;
            line-height: 1.6;
            margin-top: 15px;
        }
        
        .button-container {
            text-align: center;
            margin: 40px 0 30px;
        }
        
        .divine-btn {
            background-color: #8b4513;
            color: #f2c94c;
            border: 3px solid #c19a6b;
            border-radius: 50px;
            padding: 18px 50px;
            font-size: 1.8rem;
            font-family: "STKaiti", "华文楷体", serif;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
        }
        
        .divine-btn:hover {
            background-color: #a0522d;
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.6);
        }
        
        .divine-btn:active {
            transform: translateY(1px);
        }
        
        .footer {
            text-align: center;
            margin-top: 40px;
            padding: 25px;
            width: 100%;
            border-top: 2px solid #5c3921;
        }
        
        .wechat-info {
            font-size: 2.2rem;
            color: #f2c94c;
            margin-bottom: 10px;
        }
        
        .note {
            font-size: 1.3rem;
            color: #c19a6b;
            font-style: italic;
        }
        
        .yin-yang {
            font-size: 3rem;
            margin: 15px 0;
            color: #c19a6b;
        }
        
        .instructions {
            font-size: 1.4rem;
            color: #d4b483;
            margin-top: 20px;
            text-align: center;
            max-width: 800px;
            line-height: 1.6;
            margin-left: auto;
            margin-right: auto;
        }
        
        .border-decoration {
            position: absolute;
            width: 50px;
            height: 50px;
            border: 2px solid #c19a6b;
        }
        
        .border-1 {
            top: 20px;
            left: 20px;
            border-right: none;
            border-bottom: none;
        }
        
        .border-2 {
            top: 20px;
            right: 20px;
            border-left: none;
            border-bottom: none;
        }
        
        .border-3 {
            bottom: 20px;
            left: 20px;
            border-right: none;
            border-top: none;
        }
        
        .border-4 {
            bottom: 20px;
            right: 20px;
            border-left: none;
            border-top: none;
        }
        
        @media (max-width: 900px) {
            .gua-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 600px) {
            .gua-container {
                grid-template-columns: 1fr;
            }
            
            .header h1 {
                font-size: 3rem;
            }
            
            .gua-symbol {
                font-size: 5rem;
            }
            
            .gua-name {
                font-size: 2.2rem;
            }
            
            .container {
                padding: 20px 15px;
            }
        }
    </style>
</head>
<body>
    <div class="border-decoration border-1"></div>
    <div class="border-decoration border-2"></div>
    <div class="border-decoration border-3"></div>
    <div class="border-decoration border-4"></div>
    
    <div class="container">
        <div class="header">
            <h1>范范占卜</h1>
            <div class="subtitle">静心默念问题，点获取卦象</div>
        </div>
        
        <div class="instructions">
            《易经》六十四卦，蕴含天地万物之理。每次获取三卦，观其变化，参悟玄机。
        </div>
        
        <div class="gua-container" id="guaContainer">
            <!-- 三卦将在这里动态生成 -->
        </div>
        
        <div class="button-container">
            <button class="divine-btn" id="divineBtn">获取三卦</button>
        </div>
        
        <div class="instructions">
            点击按钮随机获取三卦，每卦各有其深意。三卦同观，可察事物之变，明进退之道。
        </div>
    </div>
    
    <div class="footer">
        <div class="yin-yang">☯</div>
        <div class="wechat-info">微信：FanX414</div>
        <div class="note">【加好友解卦】</div>
    </div>

    <script>
        // 易经64卦完整数据
        const guaList = [
            { symbol: "䷀", name: "乾为天", number: "第1卦", desc: "天行健，君子以自强不息" },
            { symbol: "䷁", name: "坤为地", number: "第2卦", desc: "地势坤，君子以厚德载物" },
            { symbol: "䷂", name: "水雷屯", number: "第3卦", desc: "云雷屯，君子以经纶" },
            { symbol: "䷃", name: "山水蒙", number: "第4卦", desc: "山下出泉，蒙。君子以果行育德" },
            { symbol: "䷄", name: "水天需", number: "第5卦", desc: "云上于天，需。君子以饮食宴乐" },
            { symbol: "䷅", name: "天水讼", number: "第6卦", desc: "天与水违行，讼。君子以作事谋始" },
            { symbol: "䷆", name: "地水师", number: "第7卦", desc: "地中有水，师。君子以容民畜众" },
            { symbol: "䷇", name: "水地比", number: "第8卦", desc: "地上有水，比。先王以建万国，亲诸侯" },
            { symbol: "䷈", name: "风天小畜", number: "第9卦", desc: "风行天上，小畜。君子以懿文德" },
            { symbol: "䷉", name: "天泽履", number: "第10卦", desc: "上天下泽，履。君子以辨上下，定民志" },
            { symbol: "䷊", name: "地天泰", number: "第11卦", desc: "天地交，泰。后以财成天地之道" },
            { symbol: "䷋", name: "天地否", number: "第12卦", desc: "天地不交，否。君子以俭德辟难" },
            { symbol: "䷌", name: "天火同人", number: "第13卦", desc: "天与火，同人。君子以类族辨物" },
            { symbol: "䷍", name: "火天大有", number: "第14卦", desc: "火在天上，大有。君子以遏恶扬善" },
            { symbol: "䷎", name: "地山谦", number: "第15卦", desc: "地中有山，谦。君子以裒多益寡" },
            { symbol: "䷏", name: "雷地豫", number: "第16卦", desc: "雷出地奋，豫。先王以作乐崇德" },
            { symbol: "䷐", name: "泽雷随", number: "第17卦", desc: "泽中有雷，随。君子以向晦入宴息" },
            { symbol: "䷑", name: "山风蛊", number: "第18卦", desc: "山下有风，蛊。君子以振民育德" },
            { symbol: "䷒", name: "地泽临", number: "第19卦", desc: "泽上有地，临。君子以教思无穷" },
            { symbol: "䷓", name: "风地观", number: "第20卦", desc: "风行地上，观。先王以省方观民设教" },
            { symbol: "䷔", name: "火雷噬嗑", number: "第21卦", desc: "雷电噬嗑，先王以明罚敕法" },
            { symbol: "䷕", name: "山火贲", number: "第22卦", desc: "山下有火，贲。君子以明庶政" },
            { symbol: "䷖", name: "山地剥", number: "第23卦", desc: "山附于地，剥。上以厚下安宅" },
            { symbol: "䷗", name: "地雷复", number: "第24卦", desc: "雷在地中，复。先王以至日闭关" },
            { symbol: "䷘", name: "天雷无妄", number: "第25卦", desc: "天下雷行，物与无妄。先王以茂对时育万物" },
            { symbol: "䷙", name: "山天大畜", number: "第26卦", desc: "天在山中，大畜。君子以多识前言往行" },
            { symbol: "䷚", name: "山雷颐", number: "第27卦", desc: "山下有雷，颐。君子以慎言语，节饮食" },
            { symbol: "䷛", name: "泽风大过", number: "第28卦", desc: "泽灭木，大过。君子以独立不惧" },
            { symbol: "䷜", name: "坎为水", number: "第29卦", desc: "水洊至，习坎。君子以常德行" },
            { symbol: "䷝", name: "离为火", number: "第30卦", desc: "明两作，离。大人以继明照于四方" },
            { symbol: "䷞", name: "泽山咸", number: "第31卦", desc: "山上有泽，咸。君子以虚受人" },
            { symbol: "䷟", name: "雷风恒", number: "第32卦", desc: "雷风，恒。君子以立不易方" },
            { symbol: "䷠", name: "天山遁", number: "第33卦", desc: "天下有山，遁。君子以远小人" },
            { symbol: "䷡", name: "雷天大壮", number: "第34卦", desc: "雷在天上，大壮。君子以非礼弗履" },
            { symbol: "䷢", name: "火地晋", number: "第35卦", desc: "明出地上，晋。君子以自昭明德" },
            { symbol: "䷣", name: "地火明夷", number: "第36卦", desc: "明入地中，明夷。君子以莅众用晦而明" },
            { symbol: "䷤", name: "风火家人", number: "第37卦", desc: "风自火出，家人。君子以言有物而行有恒" },
            { symbol: "䷥", name: "火泽睽", number: "第38卦", desc: "上火下泽，睽。君子以同而异" },
            { symbol: "䷦", name: "水山蹇", number: "第39卦", desc: "山上有水，蹇。君子以反身修德" },
            { symbol: "䷧", name: "雷水解", number: "第40卦", desc: "雷雨作，解。君子以赦过宥罪" },
            { symbol: "䷨", name: "山泽损", number: "第41卦", desc: "山下有泽，损。君子以惩忿窒欲" },
            { symbol: "䷩", name: "风雷益", number: "第42卦", desc: "风雷，益。君子以见善则迁" },
            { symbol: "䷪", name: "泽天夬", number: "第43卦", desc: "泽上于天，夬。君子以施禄及下" },
            { symbol: "䷫", name: "天风姤", number: "第44卦", desc: "天下有风，姤。后以施命诰四方" },
            { symbol: "䷬", name: "泽地萃", number: "第45卦", desc: "泽上于地，萃。君子以除戎器" },
            { symbol: "䷭", name: "地风升", number: "第46卦", desc: "地中生木，升。君子以顺德，积小以高大" },
            { symbol: "䷮", name: "泽水困", number: "第47卦", desc: "泽无水，困。君子以致命遂志" },
            { symbol: "䷯", name: "水风井", number: "第48卦", desc: "木上有水，井。君子以劳民劝相" },
            { symbol: "䷰", name: "泽火革", number: "第49卦", desc: "泽中有火，革。君子以治历明时" },
            { symbol: "䷱", name: "火风鼎", number: "第50卦", desc: "木上有火，鼎。君子以正位凝命" },
            { symbol: "䷲", name: "震为雷", number: "第51卦", desc: "洊雷，震。君子以恐惧修省" },
            { symbol: "䷳", name: "艮为山", number: "第52卦", desc: "兼山，艮。君子以思不出其位" },
            { symbol: "䷴", name: "风山渐", number: "第53卦", desc: "山上有木，渐。君子以居贤德善俗" },
            { symbol: "䷵", name: "雷泽归妹", number: "第54卦", desc: "泽上有雷，归妹。君子以永终知敝" },
            { symbol: "䷶", name: "雷火丰", number: "第55卦", desc: "雷电皆至，丰。君子以折狱致刑" },
            { symbol: "䷷", name: "火山旅", number: "第56卦", desc: "山上有火，旅。君子以明慎用刑" },
            { symbol: "䷸", name: "巽为风", number: "第57卦", desc: "随风，巽。君子以申命行事" },
            { symbol: "䷹", name: "兑为泽", number: "第58卦", desc: "丽泽，兑。君子以朋友讲习" },
            { symbol: "䷺", name: "风水涣", number: "第59卦", desc: "风行水上，涣。先王以享于帝立庙" },
            { symbol: "䷻", name: "水泽节", number: "第60卦", desc: "泽上有水，节。君子以制数度，议德行" },
            { symbol: "䷼", name: "风泽中孚", number: "第61卦", desc: "泽上有风，中孚。君子以议狱缓死" },
            { symbol: "䷽", name: "雷山小过", number: "第62卦", desc: "山上有雷，小过。君子以行过乎恭" },
            { symbol: "䷾", name: "水火既济", number: "第63卦", desc: "水在火上，既济。君子以思患而豫防之" },
            { symbol: "䷿", name: "火水未济", number: "第64卦", desc: "火在水上，未济。君子以慎辨物居方" }
        ];
        
        // 获取DOM元素
        const guaContainer = document.getElementById('guaContainer');
        const divineBtn = document.getElementById('divineBtn');
        
        // 随机选择三个不重复的卦
        function getThreeRandomGua() {
            const shuffled = [...guaList].sort(() => 0.5 - Math.random());
            return shuffled.slice(0, 3);
        }
        
        // 创建卦象卡片HTML
        function createGuaCard(gua) {
            return `
                <div class="gua-card">
                    <div class="gua-symbol">${gua.symbol}</div>
                    <div class="gua-name">${gua.name}</div>
                    <div class="gua-number">${gua.number}</div>
                    <div class="gua-desc">${gua.desc}</div>
                </div>
            `;
        }
        
        // 更新显示
        function updateDisplay() {
            const randomGua = getThreeRandomGua();
            let cardsHTML = '';
            
            randomGua.forEach(gua => {
                cardsHTML += createGuaCard(gua);
            });
            
            // 先淡出
            guaContainer.style.opacity = '0';
            
            setTimeout(() => {
                guaContainer.innerHTML = cardsHTML;
                // 淡入
                guaContainer.style.transition = 'opacity 0.5s ease';
                guaContainer.style.opacity = '1';
            }, 300);
        }
        
        // 添加点击事件
        divineBtn.addEventListener('click', function() {
            // 添加点击效果
            divineBtn.style.transform = 'scale(0.95)';
            
            // 短暂延迟后更新
            setTimeout(() => {
                updateDisplay();
                
                // 恢复按钮状态
                setTimeout(() => {
                    divineBtn.style.transform = 'scale(1)';
                }, 300);
            }, 150);
        });
        
        // 页面加载时显示三卦
        document.addEventListener('DOMContentLoaded', function() {
            updateDisplay();
        });
        
        // 添加键盘支持
        document.addEventListener('keydown', function(event) {
            if (event.code === 'Space' || event.code === 'Enter') {
                event.preventDefault();
                divineBtn.click();
            }
        });
    </script>
</body>
</html>
