<template>
    <v-container>
            <v-col cols="12" sm="6">
              <v-text-field
                label="¿Que quieres Buscar?"
                single-line
                outlined
                v-model="word"
               
              ></v-text-field>
        </v-col>
         <div class="text-center col-md-4">
                <v-btn rounded color="dark"  @click="searchItem" dark>Buscar</v-btn>
            </div>
    </v-container>
</template>
<script>

import Axios from 'axios'
export default {
    name:'Search',
    search:[],
    word:'',
    methods:{
     searchItem(){

        Axios.get("https://pixabay.com/api/?key=18325849-94cafec8b0f30985ae8cfbdde&q="+this.word+"&image_type=photo")
        .then(res=>{
            this.search = res.data;

            this.$emit("searchResult",res.data);

})
     }
        

    }
}
</script>

<style>

</style>