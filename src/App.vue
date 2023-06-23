<script setup>
import SplitBillView from './components/SplitBillView.vue';


</script>

<template>
  <SplitBillView/>
  <div class="container">
  <footer class="footer-bs">
    <p class="col-md-4 mb-0 text-body-secondary">&copy; 2023, by Julio Luna</p>
  </footer>
</div>
</template>

<style scope>
.footer-bs{
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    /* background-color: red; */
    color: white;
    text-align: center;
  }
</style>
