<template>
 <router-link :to="'/detail/'+product.id">
  <div class="card mb-10">
    <img
      class="card-img-top"
      :src="'assets/' + product.gambar"
      alt="Card image cap"
    />
    <div class="card-body">
      <h5 class="mt-0">{{ product.nama }}</h5>
      <p class="card-text">Harga : {{ product.harga || toCurrency }}</p>
      <router-link to="/" class="btn btn-sm btn-success"
        ><b-icon-cart></b-icon-cart>Pesan Sekarang</router-link
      >
    </div>
  </div>
  </router-link>
</template>

<script>
export default {
  Name: "CardProduct",
  props: ["product"],
};
// eslint-disable-next-line no-undef
</script>

<style>
</style>