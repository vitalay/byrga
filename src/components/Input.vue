
<template>
<input type="number" @input="changeAmount($event.target.value)" placeholder="Введите число">
  
</template>


<script>

export default {
    props: {
        changeAmount: Function,
        required: true
    }
}

</script>

<style scoped>

input {
    outline: none;
    width: 500px;
    position: relative;
    top: -50px;
    font-size: 1.2em;
    border: 0;
    border-radius: 3px;
    padding: 10px 15px;
    background: #fafafa;
    color: #333;
}


</style>
