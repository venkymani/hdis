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
    <a v-on:click="selection(1)">About</a>
    <a v-on:click="selection(2)">Base</a>
    <a v-on:click="selection(3)">Blog</a>
    <a v-on:click="selection(4)">Contact</a>
    <a v-on:click="selection(5)">Custom</a>
    <a v-on:click="selection(6)">Support</a>
    <a v-on:click="selection(7)">Tools</a>
  </div>


</div></div>

</template>

<script>
export default {
name: 'ProfileItem',
data() {
  return {
    docname:''};
  
},
methods:{
myFunction:function() {
  document.getElementById("myDropdown").classList.toggle("show");
},
selection:function(num)
{
console.log(num);
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
#myInput {
  box-sizing: border-box;
  background-position: 14px 12px;
  background-repeat: no-repeat;
  font-size: 16px;
  padding: 14px 20px 12px 45px;
  border: none;
  border-bottom: 1px solid #ddd;
}

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