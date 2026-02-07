<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Love 🤍</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Montserrat:wght@300;400&display=swap" rel="stylesheet">
    <style>
        :root { --pink: #ff85a1; --soft: #fff5f7; }
        body { margin: 0; font-family: 'Montserrat', sans-serif; background: var(--soft); color: #4a4a4a; overflow-x: hidden; text-align: center; }
        
        #lock { position: fixed; inset: 0; background: white; z-index: 100; display: flex; flex-direction: column; justify-content: center; align-items: center; }
        input { padding: 12px; border: 2px solid var(--pink); border-radius: 25px; margin: 10px; outline: none; text-align: center; font-size: 16px; }

        .container { max-width: 600px; margin: 0 auto; padding: 40px 20px; }
        h1 { font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: var(--pink); }

        /* Envelope Styles */
        #envelope-wrapper { display: none; margin-top: 50px; cursor: pointer; perspective: 1000px; }
        .envelope { position: relative; width: 200px; height: 130px; background: #f39c12; margin: 0 auto; border-radius: 0 0 5px 5px; transition: 0.5s; }
        .envelope::before { content: ""; position: absolute; top: 0; left: 0; border-left: 100px solid transparent; border-right: 100px solid transparent; border-top: 70px solid #e67e22; transform-origin: top; transition: 0.5s; z-index: 2; }
        .envelope.open::before { transform: rotateX(180deg); }
        .heart-seal { position: absolute; top: 40%; left: 50%; transform: translate(-50%, -50%); font-size: 30px; z-index: 3; }

        #content { display: none; opacity: 0; transition: 1s; padding-bottom: 50px; }
        .letter-paper { background: white; padding: 30px; border-radius: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); text-align: left; line-height: 1.8; font-family: 'Dancing Script', cursive; font-size: 1.3rem; white-space: pre-line; margin-top: 30px; border: 2px dashed var(--pink); }
        
        #thousand-loves { font-size: 0.9rem; color: var(--pink); opacity: 0.6; margin-top: 20px; line-height: 1.5; word-wrap: break-word; }
        .floating-heart { position: fixed; color: var(--pink); pointer-events: none; z-index: 50; animation: float 4s linear infinite; }
        @keyframes float { 0% { transform: translateY(100vh) scale(1); opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }
        
        .btn { background: var(--pink); color: white; border: none; padding: 12px 30px; border-radius: 25px; font-weight: bold; cursor: pointer; }
    </style>
</head>
<body>

    <div id="lock">
        <h1>A message for you... ✨</h1>
        <input type="password" id="pass" placeholder="Secret password">
        <button class="btn" onclick="unlock()">Open 🤍</button>
        <p style="font-size: 0.7rem; color: #ccc; margin-top: 15px;">Hint: mylove</p>
    </div>

    <div class="container">
        <div id="question-area" style="display:none;">
            <h1>Will you be my Valentine? 🌹</h1>
            <button class="btn" style="padding: 15px 40px; font-size: 1.2rem;" onclick="showEnvelope()">YES!</button>
        </div>

        <div id="envelope-wrapper" onclick="revealLetter()">
            <div class="envelope" id="env"><div class="heart-seal">❤️</div></div>
            <p>Tap the envelope to open 💌</p>
        </div>

        <div id="content">
            <h1>For You, Always 🤍</h1>
            <div class="letter-paper" id="letterText"></div>
            <div id="thousand-loves"></div>
        </div>
    </div>

    <script>
        const fullLetter = `My love,

I’ve been thinking about you a lot lately, about how you walked into my life in the most unexpected way and somehow made everything feel lighter. There are days when the world feels loud and heavy, and then there’s you—your laugh, your presence, the calm you bring even when things get messy. I don’t always say this out loud, but having you in my life is one of the things I’m most grateful for. You remind me that love doesn’t have to be perfect to be real. It just has to be honest.

Thank you for choosing me every day, even on the days when I’m not at my best. Thank you for being patient when I’m moody, tired, or quiet. Thank you for listening to my stories, even the random ones that don’t always make sense. Thank you for caring about the small details—how I’m feeling, what made me smile, what made my day hard. Those little things might seem simple, but they mean so much to me. They make me feel seen, heard, and understood.

I love how you make ordinary moments feel special. The simple talks, the jokes we share, the times we just sit and exist together—those moments are my favorite. They remind me that love isn’t only about big gestures. It’s about choosing to show up, choosing to care, choosing to stay kind even when things aren’t easy. With you, I’ve learned that comfort can be beautiful. I’ve learned that peace can feel like home.

You inspire me to be better—not in a pressured way, but in a gentle way. You make me want to grow, to be more patient, to be more understanding, to be braver with my feelings. When I doubt myself, you remind me of my worth. When I’m scared to try, you encourage me to take the step anyway. You don’t just love me; you believe in me, and that’s something I hold close to my heart.

I know we’re both still learning. We’re learning how to communicate, how to handle misunderstandings, how to be there for each other when life gets tough. There will be days when we don’t agree, days when we’re tired, days when emotions run high. But I want you to know that I choose to work through those days with you. I choose patience over pride. I choose honesty over silence. I choose us, not because we’re perfect, but because we’re willing to grow together.

If I ever get quiet, please know it doesn’t mean I love you any less. Sometimes my heart just needs a moment to breathe. And if you ever feel unsure, I hope you remember this: you matter to me. Your feelings matter to me. Your dreams matter to me. I care about the things that make you excited, the things that worry you, and the things you’re still figuring out. I want to be someone who supports you, not someone who holds you back.

I admire your strength, even when you don’t see it in yourself. I admire how you try, how you keep going, how you show up for the people you care about. You don’t have to be perfect for me to love you. I love you for who you are, for the effort you give, for the heart you carry. And on the days you feel like you’re not enough, I hope you hear my voice in your mind telling you that you are more than enough.

Being with you makes me hopeful about the future—not in a pressured way, but in a gentle, steady way. I imagine more shared laughs, more late-night talks, more quiet moments where everything feels okay because we’re together. I don’t know exactly what tomorrow will bring, but I know I want to face it with you by my side, learning, growing, and choosing each other again and again.

Thank you for being my safe place. Thank you for being my comfort. Thank you for being my favorite person to talk to when my day has been long. Thank you for reminding me that love can be kind, patient, and real. I promise to keep trying to be someone who listens, who understands, and who shows love not just with words, but with actions.

No matter how busy life gets, no matter how loud the world becomes, I hope you always remember this: you are important to me. You are valued. You are cared for deeply. I’m proud of you for who you are and for who you’re becoming. And I’m grateful that out of all the people in this world, I get to walk this part of life with you.

With all my love,
Always yours 🤍`;

        function unlock() {
            if(document.getElementById('pass').value.toLowerCase() === "mylove") {
                document.getElementById('lock').style.display = "none";
                document.getElementById('question-area').style.display = "block";
            } else { alert("Try again, beautiful! 🌸"); }
        }

        function showEnvelope() {
            document.getElementById('question-area').style.display = "none";
            document.getElementById('envelope-wrapper').style.display = "block";
        }

        function revealLetter() {
            document.getElementById('env').classList.add('open');
            setTimeout(() => {
                document.getElementById('envelope-wrapper').style.display = "none";
                document.getElementById('content').style.display = "block";
                setTimeout(() => document.getElementById('content').style.opacity = "1", 50);
                
                // 1000 Love Yous
                let loves = "";
                for(let k=0; k<1000; k++) loves += "I love you. ";
                document.getElementById('thousand-loves').textContent = loves;

                setInterval(createHeart, 300);
                typeWriter();
            }, 600);
        }

        let charIdx = 0;
        function typeWriter() {
            if (charIdx < fullLetter.length) {
                document.getElementById('letterText').textContent += fullLetter.charAt(charIdx);
                charIdx++;
                setTimeout(typeWriter, 30);
                if (charIdx % 10 === 0) window.scrollTo(0, document.body.scrollHeight);
            }
        }

        function createHeart() {
            const h = document.createElement('div');
            h.classList.add('floating-heart');
            h.innerHTML = ['❤️', '💖', '🤍', '🌸'][Math.floor(Math.random() * 4)];
            h.style.left = Math.random() * 100 + "vw";
            document.body.appendChild(h);
            setTimeout(() => h.remove(), 4000);
        }
    </script>
</body>
</html>
