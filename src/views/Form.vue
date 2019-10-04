<template>
  <section>
    <Navbar />
    <v-container mt-4>
      <v-layout wrap>
        <v-flex md6 sm12 xs12 px-2>
          <v-form id="form" @submit.prevent="enviarFormulario">
            <h2>Formulario de vehiculos</h2>
            <v-text-field
              v-model="marca"
              :error-messages="errorMarca"
              placeholder="Ingrese la marca"
              label="Marca"
            />
            <v-text-field
              v-model="modelo"
              :error-messages="errorModelo"
              placeholder="Ingrese el modelo"
              label="Modelo"
            />
            <v-text-field
              v-model="color"
              :error-messages="errorColor"
              placeholder="Ingrese el color"
              label="Color"
            />
            <v-btn dark type="submit" form="form">Enviar</v-btn>
          </v-form>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
import Navbar from "../components/Navbar.vue";
export default {
  components: {
    Navbar
  },

  data() {
    return {
      productos: [],
      marca: "",
      modelo: "",
      color: "",
      errorMarca: "",
      errorModelo: "",
      errorColor: ""
    };
  },

  methods: {
    enviarFormulario() {
      let validar = true;
      if (this.marca === "") {
        this.errorMarca = "La marca es requerida";
        validar = false;
      } else {
        this.errorMarca = "";
      }

      if (this.modelo === "") {
        this.errorModelo = "El modelo es requerido";
        validar = false;
      } else {
        this.errorModelo = "";
      }
      if (this.color === "") {
        this.errorColor = "El color es requerido";
        validar = false;
      } else {
        this.errorColor = "";
      }

      if (validar) {
        this.productos.push({
          marca: this.marca,
          modelo: this.modelo,
          color: this.color
        });
        this.marca = "";
        this.modelo = "";
        this.color = "";

        this.errorMarca = "";
        this.errorModelo = "";
        this.errorColor = "";
      }
      console.log(this.productos);
    }
  }
};
</script>