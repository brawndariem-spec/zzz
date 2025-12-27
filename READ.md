<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>提示信息</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Microsoft YaHei', '微软雅黑', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            position: relative;
            overflow: hidden;
        }
        
        .bg-decoration {
            position: absolute;
            border-radius: 50%;
            opacity: 0.1;
            z-index: -1;
        }
        
        .circle-1 {
            width: 300px;
            height: 300px;
            background: linear-gradient(45deg, #ff9a9e, #fad0c4);
            top: -100px;
            left: -100px;
        }
        
        .circle-2 {
            width: 400px;
            height: 400px;
            background: linear-gradient(45deg, #a1c4fd, #c2e9fb);
            bottom: -200px;
            right: -100px;
        }
        
        .circle-3 {
            width: 200px;
            height: 200px;
            background: linear-gradient(45deg, #ffecd2, #fcb69f);
            bottom: 50px;
            left: 10%;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            text-align: center;
        }
        
        .title {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            position: relative;
            display: inline-block;
        }
        
        .title:after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(to right, #ff9a9e, #a1c4fd);
            border-radius: 2px;
        }
        
        .message-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 40px 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .message-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }
        
        .message-text {
            font-size: 1.8rem;
            line-height: 1.6;
            color: #444;
            margin-bottom: 20px;
            font-weight: 500;
            position: relative;
            z-index: 2;
        }
        
        .message-text span.highlight {
            color: #ff6b6b;
            font-weight: 600;
            position: relative;
        }
        
        .message-text span.highlight:after {
            content: '';
            position: absolute;
            bottom: 2px;
            left: 0;
            width: 100%;
            height: 8px;
            background-color: rgba(255, 107, 107, 0.2);
            z-index: -1;
        }
        
        .decoration {
            position: absolute;
            font-size: 6rem;
            opacity: 0.1;
            color: #ff9a9e;
            z-index: 1;
        }
        
        .decoration.left {
            top: 20px;
            left: 20px;
        }
        
        .decoration.right {
            bottom: 20px;
            right: 20px;
        }
        
        .footer {
            margin-top: 30px;
            font-size: 1rem;
            color: #666;
            opacity: 0.8;
        }
        
        @media (max-width: 768px) {
            .title {
                font-size: 2rem;
            }
            
            .message-text {
                font-size: 1.5rem;
            }
            
            .decoration {
                font-size: 4rem;
            }
        }
        
        @media (max-width: 480px) {
            .title {
                font-size: 1.7rem;
            }
            
            .message-text {
                font-size: 1.3rem;
            }
            
            .message-card {
                padding: 30px 20px;
            }
        }
        
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
        
        .message-card {
            animation: float 5s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <div class="bg-decoration circle-1"></div>
    <div class="bg-decoration circle-2"></div>
    <div class="bg-decoration circle-3"></div>
    
    <div class="container">
        <h1 class="title">温馨提示</h1>
        
        <div class="message-card">
            <div class="decoration left">❤</div>
            <div class="decoration right">⚠</div>
            
            <div class="message-text">
                <span class="highlight">小傻瓜</span>，群主不开群成员邀请人的功能，所以我没办法哦～
            </div>
            
            <div class="message-text" style="font-size: 1.4rem; margin-top: 20px;">
                需要联系群主开启该功能后，才能邀请新成员加入。
            </div>
        </div>
        
        <div class="footer">
            本页面仅用于显示提示信息 | 自动适应各种屏幕尺寸 | 作者:红姜一定要尝
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const messageCard = document.querySelector('.message-card');
            
            messageCard.addEventListener('click', function() {
                this.style.transform = 'scale(0.98)';
                setTimeout(() => {
                    this.style.transform = '';
                }, 200);
            });
            
            const decorations = document.querySelectorAll('.decoration');
            decorations.forEach(decoration => {
                if(decoration.classList.contains('left')) {
                    decoration.style.top = Math.random() * 60 + 10 + 'px';
                } else {
                    decoration.style.bottom = Math.random() * 60 + 10 + 'px';
                }
            });
        });
    </script>
</body>
</html>
