<template>
  <v-container>
    <v-row class="text-center">


      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Make it better. Mock it.
        </h1>
      </v-col>

    </v-row>
    <v-row>
      <v-col>
        <v-textarea solo v-model="input" placeholder="Hey hi! This is not serious" v-on:change="translate"></v-textarea>      
      </v-col>
      <v-col>
        <v-textarea disabled v-model="output" solo-inverted placeholder="Hey HI! tHis is not SeRiOUS"/>
      </v-col>
    </v-row>
    <v-row justify="center">
        <v-btn v-on:click="translate" color="primary">Translate</v-btn>
    </v-row>
  </v-container>
</template>

<script>
import axios from 'axios'
  export default {
    name: 'MainPage',

    data: () => ({
      input: '',
      output: ''
    }),
    methods: {
      translate: function () {

        axios({
          method: 'post',
          url: 'https://mock-this.herokuapp.com',
          data: {
            'message': this.input
          },
          headers: {
            "Content-Type": 'application/json',
            "Access-Control-Allow-Origin": "*"
          },
        }).then(response => (this.output = response.mock))
      }
    }
  }
</script>
