<template>
  <div>
    <div class="tollcontainer">
      <div class="tollheader">
        <h1>Toll entries</h1>
        <span class="material-symbols-outlined" @click="showdropdown">
          filter_alt
        </span>
        <div class="dropdown" v-if="isdropdown">
          <select v-model="selectvalue">
            <option v-for="option in optionvehicle" :key="option.id">
              {{ option.key }}
            </option>
          </select>
        </div>
        <input type="text" v-model="search" placeholder="Search Vehicles" name="vehicle"  />
      </div>
      <div class="tollbutton">
        <button @click="addvehicle" :optionvehicle="optionvehicle"  :optionvehicletype="optionvehicletype">Add vehicle entry</button>
        <button @click="viewtolls">View all tolls</button>
      </div>
    </div>
    <div class="tolltable">
      <table class="table">
        <thead>
          <tr>
            <th>VEHICLE TYPE</th>
            <th>VEHICLE NUMBER</th>
            <th>DATE/TIME</th>
            <th>TOLL NAME</th>
            <th>TARIFF</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="vehicle in filtervalue" :key="vehicle.id">
            <td>{{ vehicle.vehicletype }}</td>
            <td>{{ vehicle.vehiclenumber }}</td>
            <td>{{ vehicle.date }}</td>

            <td>{{ vehicle.tollnumber }}</td>

            <td>
              {{ vehicle.tariff }}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <Vehicle v-if="isVehicle" @close="isVehicle = false"  :optionvehicle="optionvehicle"  :optionvehicletype="optionvehicletype" :vehicles="vehicles"/>
    <Viewtoll v-if="isView"  :tollsvehicle="tollsvehicle" @close="isView = false"/>
  </div>
</template>
<script>
// import data from "@/data.json"
import Vehicle from "./Vehicle.vue";
import Dropdown from "./Dropdown.vue";
import Viewtoll from './Viewtoll.vue';
export default {
  name: "Tollheader",
  components: {
    Vehicle,
    Dropdown,
    Viewtoll
  },
  props: ["vehicles", "optionvehicle","optionvehicletype","tollsvehicle"],

  data() {
    return {
      isVehicle: false,
      isdropdown: false,
      isView:false,
      selectvalue: "",
      search:''
    };
  },
  computed: {
    // filtervalue() {
     
    //   if (this.selectvalue != "All") {
    //    let filtervalue= this.vehicles.filter((vehicleObj) => {
    //       return vehicleObj["TOLL NAME"] == this.selectvalue;
    //     });
    //    this.vehicles=filtervalue
    //   }
     
    // },

    filtervalue:function(){
     
      if(this.selectvalue != "All"){
       return this.vehicles.filter((vehicleObj)=>{
           return vehicleObj.tollnumber == this.selectvalue;
       })
      }else{
        return this.vehicles;
      }
    
    
  
    }
  },
  methods: {
    addvehicle() {
      console.log("I am adding");
     
      this.isVehicle = !this.isVehicle;
    },
    showdropdown() {
      console.log("I am showing dropdown");
      this.isdropdown = !this.isdropdown;
    },
    viewtolls(){
       this.isView=!this.isView;
    }
  },
};
</script>

<style scoped>
.tollcontainer {
  display: flex;
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