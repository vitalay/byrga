<template>
  <h1>CAYPTO</h1>

  <Input />
 <div className="selector">
  <Selector />
  <Selector />

 </div>
 

</template>

<script>
import Input from "./components/Input.vue"
import Selector from "./components/Selector.vue"

export default {
  components: {
    Input,
    Selector
  },
};
</script>

<style scoped>

.selector {
    display: flex;
    justify-content: space-around;
    width: 700px;
    margin: auto;
}

</style>
