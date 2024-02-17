#index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
     <script src="https://kit.fontawesome.com/f30fac2c61.js" crossorigin="anonymous"></script>
    <link href="https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Catamaran:wght@200&family=Courgette&family=Edu+TAS+Beginner:wght@700&family=Lato:wght@300;900&family=Mukta:wght@700&family=Mulish:wght@300&family=Open+Sans&family=PT+Sans:ital,wght@1,700&family=Poppins:wght@300&family=Raleway:wght@100&family=Roboto+Condensed:wght@700&family=Roboto+Slab&family=Roboto:wght@300;400&family=Source+Sans+Pro:wght@300&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="todo.css">
</head>
<body>
   <div class="container">
    <h1>ToDo App</h1>
    <div class="inputs">
        <input type="text" placeholder="Enter Your Task" id="inp">
        <button onclick="Add()">Add</button>
    </div>
    <div class="text">
        
    </div>
   </div>

    <script src="todo.js"></script>
</body>
</html>



#todo.css
body{
    background-color: rgb(4, 29, 29);
    font-family: 'Poppins', sans-serif;
 }
 .container{
    width: 360px;
    padding: 33px;
    text-align: center;
    background-color: #fff;
    margin-left: 33%;
    margin-top: 5px;
 }
 input{
    width: 270px;
    padding: 8px;
    border: 2px solid rgb(6, 145, 145);
    outline: none;
    font-size: 19px;


 }
 button{
    width: 60px;
    height: 41px;
    background-color: rgb(4, 29, 29);
    color: white;
    border: none;
    cursor: pointer;

    outline: none;
    border-radius: 2px;
    font-size: 19px;
 }
 .text ul{
    position: relative;
    background-color: rgb(5, 31, 31);
    color: white;
    font-size: 19px;
    padding: 7px;
    text-align: left;
 }
 .text ul i{
    position: absolute;
    right: 10px;
    cursor: pointer;
 }


#todo.js

let inputs = document.getElementById("inp");
let text = document.querySelector(".text");

function Add(){
    if(inputs.value == ""){
        alert("Please Enter Task")
    }else{
        let newEle = document.createElement("ul");
        newEle.innerHTML=`${inputs.value} <i class="fa-solid fa-trash"></i>`;
        text.appendChild(newEle);
        inputs.value="";
        newEle.querySelector("i").addEventListener("click" , remove);
        function remove(){
            newEle.remove()
        }
    }
}


