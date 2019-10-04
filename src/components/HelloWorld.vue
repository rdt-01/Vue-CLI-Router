<template>
  <v-container>
    <v-layout text-center wrap>
      <v-flex xs12>
        <v-img :src="require('../assets/logo.svg')" class="my-3" contain height="200"></v-img>
      </v-flex>
      <v-btn block text to="/tabla">Tabla</v-btn>
      <v-btn block text to="/form">Formulario</v-btn>
    </v-layout>
  </v-container>
</template>
