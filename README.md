validatie.js

function validate()
{

const fname = document.reg_form.fname;
const lname = document.reg_form.lname;
var address = document.reg_form.address;
var gender = document.reg_form.gender;
var email = document.reg_form.email;
var mobile = document.reg_form.mobile;
var course = document.reg_form.course;
if (fname.value.length <= 0)
{
alert("Name is required"); fname.focus();
return false;
}
if (lname.value.length <= 0)
{
alert("Last Name is required"); lname.focus();
return false;
}
if (address.value.length <= 10)
{
alert("Address is required");address.focus();
return false;
}
if (gender.value.length <= 0)
{ alert("Gender is required"); gender.focus();
return false;
}
if(email.value.length <= 0)
{
alert("Email Id is required"); email.focus();
return false;
}
if(!(email.value.includes("@")) || (!email.value.includes(".")) || (!email.value.includes("gmail")))
{
alert("invalid email");
return false;
}
if(mobile.value.length <= 0)
{
alert("Mobile number is required");mobile.focus();
return false;
}
if(course.value == "select course")
{
alert("Course is required");course.focus();

return false;
}
alert("Registration successful")
return false;
}

Main.html
<html>
<head>
<title>Reg Form</title>
<link rel="stylesheet" href="style.css" type="text/css">
</head>
<body>
<center><h1>Form validation using HTML,CSS,JS</h1></center>
<hr>
<form method="post" name="reg_form" onsubmit= "validate()">
<h2>Registration Form</h2>
<table>
<tr>
<td><label>First Name: </label></td>
<td>
<input type="text" name="FNAME" id="fname" placeholder="First Name" pattern="[A-Za-z]+"
maxlength="15" required>
</td>
</tr>
<tr>
<td><label>Last Name: </label></td>
<td>
<input type="text" name="LNAME" id="lname" placeholder="Last Name" pattern="[A-Za-z]+"
maxlength="10" required>
</td>
</tr>
<tr>
<td><label>Address: </label></td>
<td>
<input class="Address" type="textarea" size="50" name="address" placeholder="address"
pattern="^(?=\S*\s)(?=[^a-zA-Z]*[a-zA-Z])(?=\D*\d)[a-zA-Z\d\s',.#/-]*$" required>
</td>
</tr>
<tr>
<td><label>Gender: </label></td>

<td>
<input type="radio" name="gender" value="male" required >Male
<input type="radio" name="gender" value="female" required>Female
</td>
</tr>
<tr>
<td><label>Email Id: </label></td>
<td>
<input class="Email" type="email" id="email" name="email"
pattern="[a-z0-9._%+\-]+@[a-z0-9.\-]+\.[a-z]{2,}$" required>
</td>
</tr>
<tr>
<td><label>Mobile: </label></td>
<td>
<input class="Mobile" type="tel" name="mobile" maxlength="10"
pattern="^[+]{1}(?:[0-9\\-\\(\\)\\/ \\.]\\s?){6,15}[0-9]{1}$" required />
</td>
</tr>
<td><label>Course: </label></td>
<td>
<select name="course" class="Course" required>
<option value="select course">select course</option>
<option value="HTML">HTML</option>
<option value="CSS">CSS</option>
<option value="JavaScript">JAVASCRIPT</option>
<option value="Java">JAVA</option>
</select>
</td>
</tr>
<tr>
<td>
<input type="submit" name="submit" value="Submit" onsubmit="return validate()">
<input type="reset"name="reset"value="Reset">
</td>
</tr>
</table>
</form>
<script src="validate.js"></script>
</body>
</html>

Style.css
body
{
font-family: Calibri;
}
label
{
font-size: 22px;
}
gender
{
font-size: 20px;
}
input[type="text"]
{
width: 250px;
}
input[type="submit"], input[type="reset"]
{
width: 77px;
height: 27px;
position: relative;left: 180px;
margin: 13px;
}
.course
{
width: 73%;
}
form
{
text-align: center;
font-family: Calibri;
font-size: 20px;
border: 3px solid black;
width: 600px;
margin: 20px auto;
}
.Address
{
width: 73%;
}
.Email
{
width: 73%;

}
.Mobile
{
width: 73%;
}
td
{
padding: 10px;
}
td:first-child
{
text-align: right;
font-weight: bold;
}
td:last-child
{
text-align: left;
}
