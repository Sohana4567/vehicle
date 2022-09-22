<template>
<div>
   <select v-model="selectvalue">
    <option v-for="option in optionvehicle"  :key="option.id">{{option.key}}</option>
  
</select>

</div>

</template>
<script>
export default{
name:"Dropdown",
props:['optionvehicle'],
data(){
    return{
        selectvalue:""
    }
},
// computed:{
//     filtervalue(){
//         if(this.selectvalue!="All"){
//             let filtervalue=
//         }
//     }
// }

}
</script>
