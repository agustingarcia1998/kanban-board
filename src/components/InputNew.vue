<script setup>
import { ref, defineEmits } from 'vue';



const text = ref('');
const emits = defineEmits(["onNewItem"]);

function handleSubmit(){
    if(text !== ''){
        //llama a emit
        emits('onNewItem', text);
        text.value = '';
    }
}
</script>


<template>
    <form action=""@submit.prevent = "handleSubmit">
    <input type="text" v-model="text">
    </form>
</template>


<style>

form{
    margin-bottom: 10px;
}

input{
    width: 100%;
    box-sizing: border-box;
}

</style>