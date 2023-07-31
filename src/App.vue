<template>
    <HelloWorld 
    @update-name='name => display(name)'
    />

    <span>{{ sentence }}</span>

    <br>
    <br>


    <!-- v-model permet d'associer une variable a l'input -->
    <input type="text" v-model="name">
    <input type="text" v-model="age">
</template>


<script setup>

import HelloWorld from './components/HelloWorld.vue'
// ref permet de faire reference à une variable  
//  reactive permet de rendre une variable reactive c'est a dire qu'elle sera mise a jour dans le template
import {watch, computed, ref} from 'vue'

const display = ( name ) => {
    console.log('app.vue : ' + name)
}

const sentence = computed(() => {
return `Bonjour je m'appelle ${name.value} et j'ai ${age.value} ans`
})


const name = ref('John')
const age = ref(29)

watch(name, (newValue, oldValue) => {
    console.log('name changed from ' + oldValue + ' to ' + newValue)
})


</script>



<style scoped>
.bold {
    font-weight: bold;
}

.text-red {
    color: indianred;
}

.text-green {
    color: green;
}
</style>
