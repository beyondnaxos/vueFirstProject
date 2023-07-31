<template>
    <h1>Hello world</h1>

    {{ name }}

    <input type="text" v-model="name" @input="handleUpate">
    <slot name="name">

    </slot>
    <slot name="age">

    </slot>
</template>
    
    
<script setup>
import { ref } from 'vue';

const emit = defineEmits(['updateName'])

const handleUpate = (event) => {
emit('updateName', event.target.value)
}

const name = ref('' )
</script>
    
    
    
  