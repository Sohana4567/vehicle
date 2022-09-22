<template>
  <div class="modal is-active">
    <div class="modal-background"></div>
    <div class="modal-content">
      <div class="vehicle">
        <form>
          <label>Toll Name:</label>
           <input
            type="text"
            id="tollname"
            name="tollname"  
          />
      
          <label>Vehicle fare details:</label>
         <select v-model="vehicletype">
            <option v-for="option in optionvehicletype" :key="option.id">
              {{ option.vehiclestype }}
            </option>
          </select>
           <input
            type="text"
            id="returnjourney"
            name="Return Journey"  
          />
           <input
            type="text"
            id="singlejourney"
            name="Single Journey"  
          />
          <select v-model="vehicletype">
            <option v-for="option in optionvehicletype" :key="option.id">
              {{ option.vehiclestype }}
            </option>
          </select>
           <input
            type="text"
            id="returnjourney"
            name="Return Journey"  
          />
           <input
            type="text"
            id="singlejourney"
            name="Single Journey"  
          />
          <select v-model="vehicletype">
            <option v-for="option in optionvehicletype" :key="option.id">
              {{ option.vehiclestype }}
            </option>
          </select>
           <input
            type="text"
            id="returnjourney"
            name="Return Journey"  
          />
           <input
            type="text"
            id="singlejourney"
            name="Single Journey"  
          />
          <select v-model="vehicletype">
            <option v-for="option in optionvehicletype" :key="option.id">
              {{ option.vehiclestype }}
            </option>
          </select>
           <input
            type="text"
            id="returnjourney"
            name="Return Journey"  
          />
           <input
            type="text"
            id="singlejourney"
            name="Single Journey"  
          />
         
          <button type="submit">Add Details</button>
        </form>
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
export default {
  name: "Vehicle",
  props:['optionvehicle','optionvehicletype','vehicles'],
  data() {
    return {
     tollnumber:"",
     vehicletype:"",
     vehiclenumber:""
    };
  },
  methods: {
    closemodal() {
      this.$emit("close");
    },
    addtoentry(){
      console.log(this.tollnumber);
      console.log(this.vehicletype);
      this.vehicles.push({
        tollnumber:this.tollnumber,
        vehicletype:this.vehicletype,
        vehiclenumber:this.vehiclenumber
      })
    }
  },
};
</script>
<style scoped>
.vehicle {
  border: 1px solid gray;
  max-width: 600px;
  margin: auto;
  padding: 10px;
  font-size: 18px;
  font-weight: bold;
  background: white;
}
/* .product {
  background-color: #4180c5;
  text-align: center;
  max-width: 600px;
  color: aliceblue;
  padding: 10px;
  margin: auto;
  border: 1px solid gray;
  border-bottom: none;
}
.product h1 {
  margin: 0;
  padding: 15px;
} */
form {
  margin-top: 15px;
}
input[type="text"] {
  margin-bottom: 20px;
  margin-top: 10px;
  width: 100%;
  padding: 15px;
  border-radius: 5px;
  border: 1px solid #7ac9b7;
  font-size: 18px;
}
button {
  border-radius: 16px;
  background-color: #4180c5;
}
.modal{
  background: chocolate;
}
</style>