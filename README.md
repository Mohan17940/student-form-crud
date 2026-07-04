<html>
    <head>
        <title>STUDENT info
        </title>
    </head>
    <body style="background-color: aqua;">
       
   <center>
       <h1>STUDENT FORM</h1>
        <form id="formtag"  >
    <table   border="2PX" style="width: 500px; height: 200px;">
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
