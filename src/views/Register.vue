<template>
<br/><br/>
  <div class="searchorreg">

  <br/><br/>  
  <h3>Existing User?</h3>
  
  <div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2 ">
  <input type="text" class="form-control" placeholder="Enter your UHID" aria-label="UHID" aria-describedby="basic-addon2">
  <div class="input-group-append">
    <button class="btn btn-primary" type="button">Search</button>
  </div>
</div>



  </div>
  <br/>
<h5>OR</h5>
  <br/>
 <h3>Register new User</h3>

<div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2 ">
<input v-model="usrname" type="text" class="form-control" placeholder="Name" aria-label="UHID" aria-describedby="basic-addon2">

</div>
</div> 



<div class="row d-flex justify-content-center m-2">
<div class="input-group col-md-2 ">
  <input type="text" class="form-control" placeholder="Mobile" aria-label="UHID" aria-describedby="basic-addon2">
  
</div>
</div>

<div class="row justify-content-center m-2">
<div class="input-group  col-md-2"> <!-- Date input -->
        <datepicker placeholder="Date of Birth" class="form-control"
    v-model="selected"
    
  />
      </div>
</div>
<br/><br/>
<div class="row justify-content-center m-2">
    <button class="btn btn-success" id="verify" type="button" v-on:click="loadData" >Register Now</button>
  </div>
  </div>

</template>

<script>


import Datepicker from "vue3-datepicker";

import router from "@/router"

export default {
name: 'SearchorReg',


components: {
  Datepicker
},
data() {
  return {
    selected: new Date(),
    usrname:''};
  
},
methods: {
    loadData: function (event) {
      console.log(event);
      router.push({ path: 'profile', name: 'profile', params: { username: this.usrname } });
    }


},

}
</script>

<style>

</style>