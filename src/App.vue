<template>
  <h1>CRYPTO</h1>

  <Input :changeAmount="changeAmount" />
 

  <div className="selector">
    <Selector :setCrypto="setCryptoFirst" />
    <Selector :setCrypto="setCryptoSecond" />
  </div>
</template>

<script>
import Input from "./components/Input.vue"
import Selector from "./components/Selector.vue"

export default {
  components: { Input, Selector },
   data() {
     return {
       amount: 0,
       cryptoFirst: '',
       cryptoSecond: ''

     }
   },

   methods: {
    changeAmount( val ) {
      this.amount = val

    },

   setCryptoFirst( val ) {
      this.cryptoFirst = val

},

setCryptoSecond( val ) {
      this.cryptoSecond = val

},
}
}
</script>

<style scoped>
.selector {
  display: flex;
  justify-content: space-around;
  width: 700px;
  margin: auto;
}
</style>
