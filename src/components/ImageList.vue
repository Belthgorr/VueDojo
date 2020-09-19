<template>
  <v-container>
    <v-row>
      <v-col v-bind:key="item.id" v-for="item in items.hits">
        <v-card >
 <img :src="item.previewURL" alt />
<v-card-title>{{item.user}}</v-card-title>
 <v-card-subtitle> {{item.tags}}</v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {

    name: "imageList",
    props:["items"]

}
</script>

<style>

</style>