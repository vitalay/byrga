
<template>
<input min="0" type="number" @input="changeAmount($event.target.value)" placeholder="Введите число"><br>
<button @click="convert()" className="color-scale-button">Конвертация</button>
  
</template>


<script>

export default {
    props: {
        changeAmount:{
        type: Function,
        required: true
        },
        convert: {
        type: Function,
        required: true
        }
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

button {
    position: relative;
    top: -20px;

}

.color-scale-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #285fa7;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: transform 0.3s ease, background-color 0.3s ease;
}

.color-scale-button:hover {
  transform: scale(1.1);
  background-color: #212388;
}

</style>
