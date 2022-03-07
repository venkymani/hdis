<template>
<br/><br/>
<div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2 ">
<table class="table table-bordered">

  <tbody>
    <tr>
      <td><b>Name</b></td>
      <td> {{ this.$route.params.username }}</td>
    </tr>
    <tr>
      <td><b>Age</b></td>
      <td>40 Yrs</td>
    </tr>
    <tr>
      <td><b>UHID</b></td>
      <td>108401456832</td>

    </tr>
  </tbody>
</table>


<h5>You have no Appointments. Please schedule one below</h5>
</div></div>
<div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2">

  
    <input v-model="docname" id="myInput" type="text" class="form-control" placeholder="Search Doctor" aria-label="UHID" aria-describedby="basic-addon2" v-on:keyup="filterFunction">
    <div id="myDropdown" class="dropdown-content">
    <a v-on:click="selection(1)">Dr Amit Mitra</a>
    <a v-on:click="selection(2)">Dr Vineet Gupta</a>
    <a v-on:click="selection(3)">Dr Malini Awasthi</a>
    <a v-on:click="selection(4)">Dr Zeeshan Khan</a>
    <a v-on:click="selection(5)">Dr Roy Mendes</a>
    <a v-on:click="selection(6)">Dr Jignesh Shah</a>
    <a v-on:click="selection(7)">Dr Akram Raza</a>
  </div>
</div></div>
   <br/><br/>Or<br/><br/>
<div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2">
    <input v-model="speciality" id="myInput2" type="text" class="form-control" placeholder="Search Speciality" aria-label="UHID" aria-describedby="basic-addon2" v-on:keyup="filterFunction2">
    <div id="myDropdown2" class="dropdown-content">
    <a v-on:click="selection2(1)">General Surgeon</a>
    <a v-on:click="selection2(2)">Cardiology</a>
    <a v-on:click="selection2(3)">Nephrology</a>
    <a v-on:click="selection2(4)">Pulmonology</a>
    <a v-on:click="selection2(5)">Gynaecology</a>
    <a v-on:click="selection2(6)">Virology</a>
    <a v-on:click="selection2(7)">Urology</a>
  </div>


</div></div>
<br/><br/>
<div class="row justify-content-center m-2">
    <button class="btn btn-success" id="proceed" type="button" v-on:click="loadData" >Proceed</button>
  </div>


</template>

<script>
export default {
name: 'ProfileItem',
data() {
  return {
    docname:'',
    speciality:''};
  
},
methods:{
myFunction:function() {
  document.getElementById("myDropdown").classList.toggle("show");
},
selection:function(num)
{
console.log(num);
switch(num)
{
case 1:
    this.docname="Dr Amit Mitra";
    break;
 case 2:
    this.docname="Dr Vineet Gupta";
    break;   
 case 3:
    this.docname="Dr Malini Awasthi";
    break;  
 case 4:
    this.docname="Dr Zeeshan Khan";
    break;  
 case 5:
    this.docname="Dr Roy Mendes";
    break;  
 case 6:
    this.docname="Dr Jignesh Shah";
    break;  
 case 7:
    this.docname="Dr Akram Raza";
    break;     
    
    
}

document.getElementById("myDropdown").classList.toggle("show");
},selection2:function(num)
{
console.log(num);
switch(num)
{
case 1:
    this.speciality="General Surgeon";
    break;
 case 2:
    this.speciality="Cardiology";
    break;   
 case 3:
    this.speciality="Nephrology";
    break;  
 case 4:
    this.speciality="Pulmonology";
    break;  
 case 5:
    this.speciality="Gynaecology";
    break;  
 case 6:
    this.speciality="Virology";
    break;  
 case 7:
    this.speciality="Urology";
    break;     
    
    
}

document.getElementById("myDropdown2").classList.toggle("show");
},
 filterFunction:function() {
       document.getElementById("myDropdown").classList.toggle("show");

  var input, filter, div, txtValue, a, i;
  input = document.getElementById("myInput");
  filter = input.value.toUpperCase();
  div = document.getElementById("myDropdown");
  a = div.getElementsByTagName("a");
  for (i = 0; i < a.length; i++) {
    txtValue = a[i].textContent || a[i].innerText;
    if (txtValue.toUpperCase().indexOf(filter) > -1) {
      a[i].style.display = "";
    } else {
      a[i].style.display = "none";
    }
  }
},
 filterFunction2:function() {
       document.getElementById("myDropdown2").classList.toggle("show");

  var input, filter, div, txtValue, a, i;
  input = document.getElementById("myInput2");
  filter = input.value.toUpperCase();
  div = document.getElementById("myDropdown2");
  a = div.getElementsByTagName("a");
  for (i = 0; i < a.length; i++) {
    txtValue = a[i].textContent || a[i].innerText;
    if (txtValue.toUpperCase().indexOf(filter) > -1) {
      a[i].style.display = "";
    } else {
      a[i].style.display = "none";
    }
  }
}

}
} 


</script>

<style>
/* Dropdown Button */
.dropbtn {
  background-color: #04AA6D;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}

/* Dropdown button on hover & focus */
.dropbtn:hover, .dropbtn:focus {
  background-color: #3e8e41;
}

/* The search field */


/* The search field when it gets focus/clicked on */
#myInput:focus {outline: 3px solid #ddd;}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f6f6f6;
  min-width: 230px;
  border: 1px solid #ddd;
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: #f1f1f1}

/* Show the dropdown menu (use JS to add this class to the .dropdown-content container when the user clicks on the dropdown button) */
.show {display:block;}
</style>