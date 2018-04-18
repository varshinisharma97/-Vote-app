<?php
$servername="localhost";
$username="root";
$password="tiger";
$db_name="vinay";
$dbh=mysqli_connect($servername,$username,$password,$db_name) or die("Error Connecting to the database");
//echo "Connected Successfully";
$query="Select candidate from voting";
$result=mysqli_query($dbh,$query) or die("Error Querying the datebase");
echo '<form id="myform">';
while($row=mysqli_fetch_array($result,MYSQLI_ASSOC))
{
echo '<input type="radio" id="name1" name="candidate" value="'.$row['candidate'].'">'.$row['candidate'].'</input><br />';
// print_r($row)."<br />";
}
echo '</form>';
?>
