# CALCULATOR
a basic calculator project using HTML , CSS AND JAVA SCRIPT
<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <style>
        body{
            font-family: sans-serif;
            background: #eee;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .box{
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.3);
        }
        #screen{
            width: 100%;
            height: 45px;
            margin-bottom: 10px;
            text-align: right;
            font-size: 18px;
            padding: 5px;
        }
        .btns{
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 5px;
        }
        button{
            height: 50px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background: #4caf50;
            color: #fff;
        }
        button:hover{
            background: #3e9143;
        }
    </style>
</head>
<body>
    <div class="box">
        <input type="text" id="screen" disabled>
        <div class="btns">
            <button onclick="clr()">C</button>
            <button onclick="back()">⌫</button>
            <button onclick="add('%')">%</button>
            <button onclick="add('/')">/</button>

            <button onclick="add('7')">7</button>
            <button onclick="add('8')">8</button>
            <button onclick="add('9')">9</button>
            <button onclick="add('*')">×</button>

            <button onclick="add('4')">4</button>
            <button onclick="add('5')">5</button>
            <button onclick="add('6')">6</button>
            <button onclick="add('-')">-</button>

            <button onclick="add('1')">1</button>
            <button onclick="add('2')">2</button>
            <button onclick="add('3')">3</button>
            <button onclick="add('+')">+</button>

            <button onclick="add('0')">0</button>
            <button onclick="add('.')">.</button>
            <button onclick="solve()">=</button>
        </div>
    </div>

    <script>
        let scr = document.getElementById("screen");

        function add(val){
            scr.value += val;
        }

        function clr(){
            scr.value = "";
        }

        function back(){
            scr.value = scr.value.substring(0, scr.value.length - 1);
        }

        function solve(){
            try{
                scr.value = eval(scr.value);
            }catch(e){
                scr.value = "Error";
            }
        }
    </script>
</body>
</html>
