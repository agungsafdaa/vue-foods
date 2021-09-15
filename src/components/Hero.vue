<template>
  <div class="row mt-2">
    <div class="col-md d-sm-block d-md-none">
      <img src="../assets/images/hero.png" class="img-fluid" />
    </div>
    <div class="col-md">
      <div class="d-flex h-100">
        <div class="justify-content-center align-self-center">
          <h2>
            <strong>Delicious Food Menu, </strong><br />
            in Your Gadget
          </h2>
          <p>Pesan Segera Menu Favorit Anda!</p>
          <router-link to="/" class="btn btn-lg btn-success"
            ><b-icon-arrow-right></b-icon-arrow-right>Pesan</router-link
          >
        </div>
      </div>
    </div>
    <div class="col-md d-none d-md-block">
      <img src="../assets/images/hero.png" class="img-fluid" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style>
</style>