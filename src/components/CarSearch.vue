<template>
  <div>
     <div class="q-gutter-md row q-pa-md">
	<div>
	   <div 
              class="text-subtitle2">Price (€)</div>
            <q-select 
              outlined  
              v-model="carSearchValue.minPrice" 
              :options="prices"  
              label="from" 
              style="width:210px"/>
	  </div>
	  <q-select 
             outlined 
             v-model="carSearchValue.maxPrice"
             :options="prices" 
             label="to" 
             style="width:210px;
             padding-top:1.4rem"/>
    </div>
 </div>
</template>

<script>
export default {
     model: {
        prop: "value",
        event: "change",
     },
     props: {
        value: Object,
     },
    data(){
	  return{
              prices:[
	           {
		      label:'500 €',
		      value:'500 €'
	           },
	          {
		      label:'1.000 €',
		      value:'1.000 €'
	           },
	           {
		      label:'1.500 €',
		      value:'1.500 €'
	           }
                 ],
             carSearchValue:{...this.value},
         }
    },
    watch:{
	    carSearchValue: function (val) {   
	   this.$emit("change", {...val});
           },
            value: function (val) {
	   this.carSearchValue={...val}
           }
    }
}
</script>