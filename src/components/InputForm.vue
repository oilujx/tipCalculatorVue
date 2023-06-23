<script setup>
import { ref } from "vue";
import {store, calculate} from "../store/store"

const total = ref(0);
const tip = ref(0);
const people = ref(0);

function handleSubmit(){
    store.params.total = total;
    store.params.tip = tip;
    store.params.people = people;
    calculate();
}

function borrar(){
    store.params.total = 0;
    store.params.tip = 0;
    store.params.people = 0;
    calculate();
    
}


</script>
<template>
    <div class="col-12 col-md-8 offset-md-2">
        <div class="h-100 p-5 text-bg-dark rounded-3">
          
          <form action="" @submit.prevent="handleSubmit">
            <div class="col-12 col-md-3 offset-md-4">
                <h2 class="text-center">Calculadora de Propinas</h2>
            </div>
            <div class="col-12 col-md-3 offset-md-4">
                    <div class="mb-2">
                        <label for="total">Total</label>
                        <input id="total" class="form-control" type="number" required v-model="total" placeholder="Password" />
                                        
                    </div>                
                </div>
                <div class="col-12 col-md-3 offset-md-4">
                    <div class="mb-2">
                        <label for="tip">% Propina</label>
                        <input class="form-control" type="number" required v-model="tip">
                    </div>
                </div>
                <div class="col-12 col-md-3 offset-md-4">
                    <div class="mb-3">
                        <label for="people"># Personas</label>
                        <input class="form-control" type="number" required v-model="people">
                    </div>
                </div>
                <div class="col-12 col-md-3 offset-md-4 text-center">
                    <div class="d-grid gap-1 d-md-block">
                        <input class="btn btn-primary" type="submit" value="Calcular" />
                        <input class="btn btn-danger" @click="borrar" type="button" value="Borrar" />
                    </div>
                    
                </div>            
            </form>
        </div>
      </div>
    
</template>
<style scoped>
/* form{
    width: 400px;
    background-color: rgb(23,129,78);
    height: 100vh;
    display: flex;
    align-items: center;
    color:white;
    font-size: 18px;
    padding: 20px;
}
.form-container{
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 20px;

}
form label{
    display: block;
}

form input{
    padding: 10px;
    width: 100%;
    box-sizing: border-box;
    font-size: 18px;
} */
</style>