<script setup>
import {store, getGrandTotal} from '../store/store'
import Label from "./Label.vue";
import Person from './Person.vue';
</script>

<template>
<div class="row align-items-center"  v-if="store.people.length >0">
    
    <div class="col-12 col-md-4 offset-md-2">
        <div class="h-100 p-1  text-bg-dark rounded-1">
            <div class="col">
                <h2 class="text-center"><b>Total + Propina:</b> ${{ getGrandTotal() }} </h2>                
            </div>
            <div class="col">
                <h3 class="text-center"><b>Faltante:</b> ${{ store.params.remaining }}</h3>
            </div>
        </div>
    </div>

    <div class="col-12 col-md-4 p-3">
        <div class="row row-cols-1 row-cols-md-4 g-1">
            <Person 
            v-for="person in store.people" :key="person.id"
            :id="person.id" 
            :number-of-person="person.numberOfPerson" 
            :total-per-person="person.totalPerPerson" 
            :paid="person.paid" 
            /> 
        </div>
    </div>
</div>
    
    
    
</template>

<style>

</style>