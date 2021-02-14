<template>
  <div>
    <car-search 
      v-model="carSearchValue"/>
    <q-btn 
      color="deep-orange"  
      label="Search" 
     @click="onClicked" />
</div>
</template>
<script>
import CarSearch from "./CarSearch.vue";
export default {
  components: { CarSearch},
  methods: {
    onClicked() {
      console.log("carSearchValue",this.carSearchValue);}
  },
 data: function () {
    return {
                   carSearchValue:{
                         minPrice:null,
                         maxPrice:null,
                   }
    }
 }
}
</script>