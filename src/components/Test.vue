<template>
  <draggable v-model="myArray" :options="{group:'people'}" @start="drag=true" @end="drag=false" id="listItem">
    <div class="colonne" v-for="element in myArray" :key="element.id">{{element.name}}</div>
   <template>
     <draggable v-model="mySecondArray" :options="{group:'people'}" @start="drag=true" @end="drag=true" id="compost">
     <div class="colonne" v-for="element in mySecondArray" :key="element.id">{{element.name}}</div>
     </draggable>
   </template>
 </draggable> 
</template>  





<script lang="ts">
import Vue from 'vue'
import draggable from 'vuedraggable'

export default Vue.extend({
  components: {
    draggable
  },
  data: function() {
    return{
      myArray: [
        {id: 1, name: 'couches'},
        {id: 2, name: 'pot de confiture'},
        {id: 3, name: "coquilles d'oeufs"},
        {id: 4, name: 'boîtes de conserve'},
        {id: 5, name: 'marc de café'}
      ],
      mySecondArray: [
           {id: 6, name: 'compost'},
        // {id: 7, name: 'carotte'},
        // {id: 8, name: "yaourt"},
        // {id: 9, name: 'carton'},
        // {id: 10, name: 'pommes'}
      ]
    }

  },
  methods:{
    
  }
})
</script>




<style>
  
  h2 {
    color: white;
  }
  #listItem {
    background-color: darkturquoise;
  }
  #prout.drop_hover {
    box-shadow: 0 0 30px rgba(0,0,0,0.8) inset;
  }
  .colonne {
    color: black;
  }
  #compost{
    background-color: maroon;
  }

</style>

<!--// npm run serve -->