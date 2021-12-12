<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
            img{
                width: 200px;
                height: 200px;
            }

            div{
                width: 250px;
                height: 250px;
                border: 1px solid #555;
            }

    </style>

    <script>
         function allowDrop(e){
            e.preventDefault();
         }

         function drag(e){
            e.dataTransfer.setData("text",e.target.id);
         }

         function drop(e){
            e.preventDefault();
            var data= e.dataTransfer.getData("text");
            e.target.appendChild(document.querySelector("#"+data));
         }
    </script>
    <title>Drag And Drop</title> 
</head>
<body>
    <div id="box" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
    <br>
    <img id="img" src="https://yt3.ggpht.com/3kmvsf3NNYy4XLy3hKc2ZVF8O-XkSaahtwUr3KW-YzJKMJsy-g2HePIayrh-JnXWbilYQ6n_=s900-c-k-c0x00ffffff-no-rj" alt="" draggable="true" ondragstart="drag(event)">
</body>
</html>
