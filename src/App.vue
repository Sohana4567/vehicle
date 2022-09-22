<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
</script>

<template>
  <div>
    <header>
      <h1 class="toll">Toll Management Application</h1>
    </header>

    <main>
      <!-- <TheWelcome /> -->
      <Tollheader :vehicles="vehicles"  :optionvehicle="optionvehicle" :optionvehicletype="optionvehicletype" :tollsvehicle=" tollsvehicle"/>
    </main>
  </div>
</template>
<script>
import Tollheader from "./components/Tollheader.vue";

export default {
  name: "App",
  components: {
    Tollheader,
  },
  data() {
    return {
      vehicles: [
        {
          id: 1,
          vehicletype: "Car/Jeep/Van",
          vehiclenumber: "TN24AQ4644",
          date: "09/09/2022,16:43:48",
          tollnumber: "Chengalpattu",
          tariff: 60,
        },
        {
          id: 2,
           vehicletype: "Car/Jeep/Van",
          vehiclenumber: "TN19QQ1234",
          date: "09/09/2022,15:30:34",
          tollnumber: "Kappalur",
          tariff: 75,
        },
        {
          id: 3,
          vehicletype: "Heavy Vehicle",
          vehiclenumber: "TN24AA1234",
          date: "09/09/2022,12:12:34",
          tollnumber: "Kappalur",
          tariff: 400,
        },
      ],
      optionvehicle:[
        {
          id:1,
          key:"All"
        },
         {
          id:2,
          key:"Kappalur"
        },
         {
          id:3,
          key:"Chengalpattu"
        },
         {
          id:4,
          key:"Krishnagiri"
        }
      ],
       optionvehicletype:[
         {
           id:1,
            vehiclestype:"Car/Jeep/Van"
         },
          {
           id:2,
            vehiclestype:"Heavy Vehicle"
         }

       ],
       tollsvehicle: [
        {
          id: 1,
          tollnumber: "Chengalpattu",
          car:60/30,
          lcv:95/50,
          truck:205/100,
          heavyvehicle:320/160
          
        },
        {
          id: 2,
          tollnumber: "Kappalur",
          car:75/50,
          lcv:125/80,
          truck:260/120,
          heavyvehicle:400/200
        },
        {
          id: 3,
           tollnumber: "Krishnagiri",
          car:70/40,
          lcv:110/65,
          truck:235/130,
          heavyvehicle:365/200
        },
      ]
    };
  },
};
</script>


<style scoped>
/* header {
  line-height: 1.5;
} */

.toll {
  border-bottom: double;
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
