<template>
  <div>
    <div class="modal is-active">
    <div class="modal-background"></div>
    <div class="modal-content">
    <div class="tollcontainer">
      <div class="tollheader">
        <h1>Tollgate List</h1>
       
      </div>
      
    </div>
    <div class="tolltable">
      <table class="table">
        <thead>
          <tr>
            <th>TOLL NAME</th>
            <th>CAR/JEEP/VAN</th>
            <th>LCV</th>
            <th>TRUCK/BUS</th>
            <th>HEAVY VEHICLE</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="toll in tollsvehicle" :key="toll.id">
            <td>{{ toll.tollnumber }}</td>
            <td>{{ toll.car }}</td>
            <td>{{ toll.lcv }}</td>

            <td>{{ toll.truck }}</td>

            <td>
              {{ toll.heavyvehicle }}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    </div>
  </div>
   <button
      class="modal-close is-large"
      @click="closemodal"
      aria-label="close"
    ></button>
  </div>
</template>
<script>
// import data from "@/data.json"

export default {
  name: "Viewtoll",
  
  props: ["vehicles", "optionvehicle","optionvehicletype","tollsvehicle"],


  methods: {
   closemodal() {
      
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.tollcontainer {
  display: flex;
   border: 1px solid gray;
  max-width: 600px;
  margin: auto;
  padding: 10px;
  font-size: 18px;
  font-weight: bold;
  background: white;
}
.tollheader {
  display: flex;
  justify-content: center;
  align-items: center;
}
input[type="text"] {
  width: 178px;
  height: 25px;
  border-radius: 25px;
  /* border: none; */
}
.tollbutton {
  display: flex;
  margin-left: 26rem;
  margin-top: 2rem;
}
button {
  margin-left: 1rem;
  margin-left: 1rem;
  /* font-size: 1rem; */
  width: 6rem;
  height: 3rem;
  border-radius: 2rem;
  background: blue;
  color: white;
}
.table-container {
  padding: 0 10%;
  margin: 40px auto 0;
}
.heading {
  font-size: 40px;

  color: black;
  margin-bottom: 40px;
}
.table {
  width: 100%;
  border-collapse: collapse;
}
.table thead {
  background-color: #ee2828;
}
.table thead tr th {
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 0.35px;
  color: #ffffff;
  opacity: 1;
  padding: 12px;
  vertical-align: top;
  border: 1px solid #dee2e685;
}
.table tbody tr td {
  font-size: 14px;
  letter-spacing: 0.35px;
  font-weight: normal;
  color: #f1f1f1;
  background-color: #3c3f44;
  padding: 8px;
  text-align: center;
  border: 1px solid #dee2e685;
}
.table .btn {
  background-color: #ff1046;
  font-weight: medium;
  color: #ffffff;
}
</style>