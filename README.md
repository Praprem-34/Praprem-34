<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>จดหมายถึงเธอ 💌</title>

<style>
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #fff0f3;
        font-family: Arial, sans-serif;
        overflow: hidden;
    }

    .container {
        text-align: center;
    }

    .letter {
        width: 280px;
        height: 190px;
        background: #ffffff;
        border-radius: 10px;
        position: relative;
        cursor: pointer;
        box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        transition: 0.3s;
    }

    .letter:hover {
        transform: translateY(-5px);
    }

    /* ฝากระดาษ */
    .flap {
        position: absolute;
        top: 0;
        left: 0;
        width: 0;
        height: 0;
        border-left: 140px solid transparent;
        border-right: 140px solid transparent;
        border-top: 100px solid #ff8fa3;
        transform-origin: top;
        transition: 0.8s;
        z-index: 3;
    }

    /* กระดาษด้านใน */
    .paper {
        position: absolute;
        width: 240px;
        height: 150px;
        background: #fffafc;
        left: 20px;
        top: 20px;
        border-radius: 8px;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
        font-size: 22px;
        color: #d94f70;
        font-weight: bold;
        opacity: 0;
        transform: translateY(20px);
        transition: 0.8s;
        z-index: 2;
    }

    /* ด้านหน้าซอง */
    .front {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 0;
        height: 0;
        border-left: 140px solid transparent;
        border-right: 140px solid transparent;
        border-bottom: 100px solid #ffb3c1;
        z-index: 4;
    }

    .hint {
        margin-top: 25px;
        color: #b84c68;
        font-size: 17px;
    }

    /* ตอนเปิด */
    .open .flap {
        transform: rotateX(180deg);
        z-index: 1;
    }

    .open .paper {
        opacity: 1;
        transform: translateY(-80px);
        z-index: 5;
    }

    .open .front {
        z-index: 1;
    }
</style>
</head>

<body>

<div class="container">

    <div class="letter" onclick="openLetter()">

        <div class="flap"></div>

        <div class="paper">
            ขอโทษนะ ❤️<br>
            เรารู้ว่าเราทำให้เธอเสียใจ
        </div>

        <div class="front"></div>

    </div>

    <div class="hint">
        💌 แตะที่จดหมายสิ
    </div>

</div>

<script>
function openLetter() {
    document.querySelector(".letter").classList.toggle("open");
}
</script>

</body>
</html>
