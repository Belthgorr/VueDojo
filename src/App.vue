<template>
 <div>
    <Toolbar/>

    <Search v-on:searchResult="searchResult"/>
    <ImageList v-bind:items="items"/>
 </div>
</template>

<script>
import Toolbar from './components/Toolbar.vue'
import Search from  './components/search.vue'
import ImageList from './components/ImageList.vue'

export default {
  name: 'App',

  components: {
    Toolbar, 
    Search,
    ImageList
  },
  methods:{

    searchResult(res){

       this.items=res;
       console.log(this.items);
    }

  },

  data: () => ({
    //
    items:[]
  }),
};
</script>
