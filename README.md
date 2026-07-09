<html>
    <head>
        <title>STUDENT info
        </title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

body{
    background:linear-gradient(135deg,#4facfe,#00f2fe);
    min-height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    padding:30px;
}

center{
    width:100%;
}

h1{
    color:white;
    margin-bottom:20px;
    font-size:35px;
    letter-spacing:2px;
    text-shadow:2px 2px 5px rgba(0,0,0,0.3);
}

form{
    background:white;
    width:100%;
    max-width:550px;
    margin:auto;
    padding:25px;
    border-radius:15px;
    box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

table{
    width:100%;
    border-collapse:collapse;
}

td{
    padding:12px;
    font-size:17px;
}

input[type="text"],
input[type="number"],
input[type="email"],
select{
    width:100%;
    padding:10px;
    border:2px solid #ddd;
    border-radius:8px;
    font-size:16px;
    transition:0.3s;
}

input:focus,
select:focus{
    border-color:#4facfe;
    outline:none;
    box-shadow:0 0 8px rgba(79,172,254,.5);
}

input[type="radio"]{
    width:auto;
    margin-right:5px;
    margin-left:10px;
}

button{
    width:100%;
    padding:12px;
    border:none;
    border-radius:8px;
    background:#4facfe;
    color:white;
    font-size:18px;
    cursor:pointer;
    transition:.3s;
    font-weight:bold;
}

button:hover{
    background:#0077ff;
    transform:scale(1.02);
}

#table{
    margin-top:30px;
    width:100%;
    max-width:900px;
    background:white;
    border-collapse:collapse;
    box-shadow:0 10px 20px rgba(0,0,0,0.2);
    border-radius:10px;
    overflow:hidden;
}

#table th,
#table td{
    border:1px solid #ddd;
    padding:12px;
    text-align:center;
}

#table tr:first-child{
    background:#0077ff;
    color:white;
    font-weight:bold;
}

#table tr:nth-child(even){
    background:#f5f5f5;
}

#table tr:hover{
    background:#d6ecff;
}

#table button{
    background:#ff4d4d;
    width:auto;
    padding:8px 15px;
    font-size:14px;
}

#table button:hover{
    background:#cc0000;
}
</style>
    </head>
    <body>
       
   <center>
       <h1>STUDENT FORM</h1>
        <form id="formtag"  >
    <table  >
        <tr >
            <td>Name</td>
            <td><input id="name" type="text" placeholder="ENTER A NAME"></td>
        </tr>
        <tr>
            <td>Age</td>
            <td><input  id="age" type="number" placeholder="ENTER YOUR AGE"></td>
        </tr>
        <tr>
            <td >Gender</td>
            
            <td><input type="radio" name="gender" value="Male" >Male
            <input type="radio" name="gender" value="Female">Female</td>
        </tr>
        <tr>
            <td>Course</td>
            <td colspan="2">
                <select  id="course" style="width: 100%;">
                    <option>java script</option>
                    <option>java</option>
                    <option>python</option>
                </select>
            </td>
        </tr>
        <tr  >
            <td >EMAIL ID</td>
            <td><input id="email" type="email" placeholder="ENTER EMAIL"></td>
        </tr>
        <tr>
    <td colspan="2">
        <button type="button" style="width:100%;" onclick="save()">Save</button>
        <style>
            button{ 
                background-color:gold;
            }
        </style>
    </td>
        </tr>
    </table>
    

</form>

    <table style="background-color: orange;width: 500px;" id="table"  border="2">
        <tr>
            <td>NAME</td>
            <td>AGE</td>
            <td>GENDER</td>
            <td>course</td>
            <td>email</td>
            <td>action</td>
        </tr>
    </table>
</center>
 </body>
</html>
<script>
     var form=document.getElementById("formtag")
     var n=document.getElementById("name")
     var age=document.getElementById("age")
      var course=document.getElementById("course")
     var email=document.getElementById("email")
     var studentTable=document.getElementById("table")  


   function save(){
    var gender=document.querySelector('input[name="gender"]:checked')
    if (gender==null){
        alert("please select gender")
        return
    }
    if(n.value=="" || age.value=="" || email.value=="")
   {
    alert("please fill all detail")
    return
   }


    var row=document.createElement("tr")
    row.innerHTML=
     "<td>"+n.value+"</td>"+
     "<td>"+age.value+"</td>"+
     "<td>"+gender.value+"</td>"+
     "<td>"+course.value+"</td>"+
     "<td>"+email.value+"</td>"+
     "<td><button onclick='deleteitem(event)'>Delete</button></td>"
      studentTable.append(row)
      form.reset()
  }


  function deleteitem(event){
    event.target.parentElement.parentElement.remove()
  }
</script>
