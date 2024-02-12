<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Do you love me?</title>
<style>
    body {
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f3f3f3;
        overflow: hidden;
    }

    #question {
        font-size: 24px;
        margin-bottom: 20px;
    }

    #noOption {
        cursor: pointer;
        transition: transform 0.5s ease;
    }

    #noOption:hover {
        transform: translateX(-10px);
    }

    #cat {
        position: absolute;
        bottom: 0;
        right: 0;
        width: 200px;
        animation: dance 2s infinite ease-in-out;
    }

    @keyframes dance {
        0% { transform: translateY(0); }
        50% { transform: translateY(-10px); }
        100% { transform: translateY(0); }
    }
</style>
</head>
<body>
    <div id="question">Do you love me?</div>
    <div id="options">
        <button onclick="alert('Yay! I love you too ❤️')">Yes</button>
        <button id="noOption" onclick="moveNo()">No</button>
    </div>
    <img id="cat" src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" alt="Dancing cat">
    
    <script>
        function moveNo() {
            alert("Oh no! Let me try to convince you!");
            var button = document.getElementById("noOption");
            var moveAmount = 10;
            var currentPosition = parseInt(getComputedStyle(button).getPropertyValue("transform").split(',')[4]);
            button.style.transform = "translateX(" + (currentPosition - moveAmount) + "px)";
        }
    </script>
</body>
</html>
