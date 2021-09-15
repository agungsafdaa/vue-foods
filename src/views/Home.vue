<template>
  <div class="home">
    <Navbar />
    <div class="container">
      <Hero />
      <div class="row mt-70">
        <div class="col-md">
          <h2>Best <strong>Foods</strong></h2>
        </div>
        <div class="col-md">
          <router-link to="/foods" class="btn btn-md btn-success float-right"
            ><b-icon-list></b-icon-list>Lihat Semua</router-link
          >
        </div>
      </div>

      <div class="row mb-3">
        <div class="col-md-4 mt-4" v-for="product in products" :key="product.id">
          <CardProduct :product="product"/>
        </div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
import Hero from "@/components/Hero.vue";
import CardProduct from "@/components/CardProduct.vue";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Navbar,
    Hero,
    CardProduct,
    Footer
  },
  data(){
    return{
      products: []
    }
  },
  methods: {
    setProduct(data){
      this.products = data
    }
  },
  mounted(){
    axios.get("http://localhost:3000/best-products")
    .then((response) =>  this.setProduct(response.data))
      // handle success
    .catch((error )=>   console.log(error))
     
  }
};
</script>
