<template>
  <div>
    <Navbar />
    <div class="container">
      <div class="row mt-4">
        <div class="col-md-12">
          <h2>Daftar <strong>Makanan</strong></h2>
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-12">
          <div class="input-group mb-2 mr-sm-2">
            <input
              v-model="search"
              type="text"
              class="form-control"
              id="inlineFormInputGroupUsername2"
              placeholder="Cari Makanan"
              @keyup="searchFood"
            />
            <div class="input-group-prepend">
              <div class="input-group-text">
                <b-icon-search></b-icon-search>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-md-3" v-for="product in products" :key="product.id">
          <CardProduct :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import CardProduct from "@/components/CardProduct.vue";
import axios from "axios";
export default {
  name: "Foods",
  components: {
    Navbar,
    CardProduct,
  },
  data() {
    return {
      products: [],
      search: "",
    };
  },
  methods: {
    setProduct(data) {
      this.products = data;
    },
    searchFood() {
      axios
        .get("http://localhost:3000/products?q=" + this.search)
        .then((response) => this.setProduct(response.data))
        // handle success
        .catch((error) => console.log(error));
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProduct(response.data))
      // handle success
      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>