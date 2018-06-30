# pixelArtMaker
<!DOCTYPE html>

<html>

<head>

    <title>Pixel Art Maker!</title>

 

    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Monoton">

 

    <link rel="stylesheet" href="styles.css">

 

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

                <script src="designs.js"></script>
</head>

<body>

    <h1>Pixel Art Maker</h1>

    <h2>Choose Grid Size</h2>
    <form id="sizePicker">

        Grid Height:
        <input type="number" id="inputHeight" name="height" min="1" value="1">
        Grid Width:

        <input type="number" id="inputWidth" name="width" min="1" value="1">


The JavaScript code

// Select color input

// Select size input

// When size is submitted by the user, call makeGrid()
 

function makeGrid(height, width) {

// Your code goes here!


  var html = "";

  for(var i = 0; i < height; i++){

    html += "<tr>";
    for(var j = 0; j < width; j++){
      html += "<td></td>";
    }
    html += "</tr>";
  }

  $("#p_Canvas").html(html);

}

$(function(){

  var height, width;

  $("#sizePicker").on('submit', function(event){

     height = $("#inputHeight").val();

     width = $("#inputWidth").val();
    
    event.preventDefault();

    makeGrid(height, width);
  });

 

  $("#p_Canvas").on('click', 'td', function(){

    var shade = $("#colorPicker").val();



    if($(this).css("background-color") == "#FFFFFF" || $(this).css("background-color") == "rgba(0, 0, 0, 0)" || $(this).css("background-color") == "rgb(255, 255, 255)") {

      $(this).css("background-color", shade);

    } else {
      $(this).css("background-color", "#FFFFFF");

    }
  })


});


The CSS Code

 body {
    text-align: center;               
	background-color:white;
}

h1 {

    font-family: Monoton;
    font-size: 70px;
    margin: 0.2em;
}

 
h2 {

    margin: 1em 0 0.25em;

                color:blue;
}

h2:first-of-type {
    margin-top: 0.5em;

}

table,

tr,

td {

    border: 1px solid black;
}


table {

    border-collapse: collapse;
    margin: 0 auto;
}

  
tr {
    height: 40px;
}


td {

    width: 40px;
}

 
input[type=number] {


    width: 6em;

}
        <input type="submit" class="button">
    </form>

    <h2>Pick A Color</h2>

 

    <input type="color" id="colorPicker">

    <h2>Design Canvas</h2>

 

    <table id="p_Canvas"></table>

</body>

 

</html>


