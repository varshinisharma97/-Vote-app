# -Vote-app
<html>
<head>
<title>Voting system</title>
<style>
body {
   background-color:TOMATO;
   text-align: center;
     }
.displaybox {
   margin: auto;
   width: 150px;
   background-color: #F4E4E3;
   border: 2px solid #000000;
   padding: 10px;
   font: 1.5em normal verdana, helvetica, arial, sans-serif;
            }

</style>

<script type="text/javascript">
var ajaxRequest=new XMLHttpRequest();
function getcandidatelist() 
{
   if (!ajaxRequest)  {
         document.getElementById("showcandidate").innerHTML = "Request error!ajax object could not be created";
         return;      }
   ajaxRequest.onreadystatechange = ajaxResponse;
   ajaxRequest.open("GET","candidates1.html");
   ajaxRequest.send();
}
function ajaxResponse()  //This gets called when the readyState changes.
{
 if (ajaxRequest.readyState != 4)  //  check to see if we're done
    {  return;  }
 else {
   if (ajaxRequest.status == 200) //  check to see if successful
        {
                 document.getElementById("showcandidate").innerHTML =
                               ajaxRequest.responseText; }
   else {
     alert("Request failed: " + ajaxRequest.statusText);
        }
   }
}
function verification()
    {
        document.getElementById("showcandidate1").innerHTML=document.getElementById("myform").elements['candidate'].value;
        alert('you have successfully casted your vote!!');
    }
var count = 0;
    function changeColor()
    {
        count++;
        var col="grey";
        if(count%2==0)
            col="blue";
        else
            col="yellow";
        document.getElementById('showcandidate').style.backgroundColor=col;
    }
</script>
</head>
<body>
    <h1>Elections</h1>

    <h2>List of contenders for the Elections of the year 2017-2018</h2>

    <form >
          <input type="button" value="Get contender list"  onclick="getcandidatelist();"/>
        <input type="button" value="Change color"  onclick="changeColor()"/>
    </form>

    <div id="showcandidate" class="displaybox">
    </div>
    <br>
    <input type="submit" value="Submit" onclick="verification();"/>
    <br>
    <br>
    <div id="showcandidate1" class="displaybox"></div>

</body>
</html>

