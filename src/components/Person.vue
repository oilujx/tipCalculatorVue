<script setup>
import {defineProps, ref} from  'vue';
import {pay} from "../store/store";
const props = defineProps(["id", "numberOfPerson", "totalPerPerson", "paid"]);
let paid = ref(false);


function handleChange(e){
    paid = e.target.checked;
    
    pay(props.id, paid);
}

</script>


<template>
  <div class="col">
    <div class="card text-center text-bg-primary">
      <div class="card-header">
        Cuate {{ props.numberOfPerson }}
      </div>
      <div class="card-body">
        <h5 class="card-title">Total a pagar</h5>
        <p class="card-text">
            {{ 
                new Intl.NumberFormat("en-US",{
                style:"currency",
                currency:"USD",
                }).format(props.totalPerPerson)  
            }}
        </p>
      </div>
      <div class="card-footer text-body-secondary">
        <input type="checkbox" @change="handleChange"/> Pago?
      </div>
    </div>
  </div>
</template>

<style scoped>
.person{
    height: 200px;
    border-radius: 5px;
    font-size: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    overflow: hidden;
}

.person-paid{
    border:solid 3px yellowgreen
}
.person-no-paid{
    border:solid 3px #ccc
}

.person-number{
    background-color: black;
    padding: 10px;
    color: white;
    text-align: center;
}

.person-to-pay{
    text-align: center;
    font-size: 30px;
    font-weight: bolder;
    color:yellowgreen;
}
.paid{
    background-color: #343f68;
    padding: 10px;
}


</style>