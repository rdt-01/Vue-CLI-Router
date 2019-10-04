<template>
  <section>
     <Navbar />
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Marca</th>
          <th class="text-left">Modelo</th>
          <th class="text-left">Color</th>
        </tr>
        
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.name">

          <td>{{ item.marca }}</td>
          <td>{{ item.modelo }}</td>
          <td>{{ item.color }}</td>

        </tr>
      </tbody>
    </template>
  </v-simple-table>
  </section>
</template>


<script>
import products from "../assets/products.json";
import Navbar from "../components/Navbar.vue";

export default {
  components: {
    Navbar
  },
  data() {
    return {
      items: products
    };
  }
};
</script>