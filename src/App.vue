<template>
  <h1>CRYPTO</h1>

  <Input :changeAmount="changeAmount" :convert="convert" :favourite="favourite"/>
 <p v-if="error !== ''"> {{ error }} </p>
 <p v-if="result !== 0" className="result-text"> {{ result }} </p>

  <Favourite :favs="favs" v-if="favs.length > 0" :getFromFavs="getFromFavs"/>



  <div className="selector">
    <Selector :setCrypto="setCryptoFirst" :cryptoNow="cryptoFirst" />
    <Selector :setCrypto="setCryptoSecond" :cryptoNow="cryptoSecond" />
  </div>
</template>

<script>
import Input from "./components/Input.vue"
import Selector from "./components/Selector.vue"
import Favourite from "./components/Favourite.vue"
import CryptoConvert from 'crypto-convert';

const convert = new CryptoConvert();



export default {
  components: { Input, Selector, Favourite },
   data() {
     return {
       amount: 0,
       cryptoFirst: '',
       cryptoSecond: '',
       error: '',
       result: 0,
       favs: []

     }
   },

   methods: {
    favourite() {
  this.favs.push({
    from: this.cryptoFirst,
    to: this.cryptoSecond
  })
    },
    getFromFavs(index) {
      
      this.cryptoFirst = this.favs[index].from
      this.cryptoSecond = this.favs[index].to
    },
    changeAmount( val ) {
      this.amount = val

    },

   setCryptoFirst( val ) {
      this.cryptoFirst = val

},

setCryptoSecond( val ) {
      this.cryptoSecond = val

},
async convert() {
    
     if (this.amount <= 0) {
         this.error = 'Введите число больше 0'
         return;
     } else {
         if (this.cryptoFirst == this.cryptoSecond) {
         this.error = 'Выберите разные криптовалюты'
         return;
     }else if (this.cryptoFirst == '' || this.cryptoSecond == '') {
         this.error = 'Выберите криптовалюту'
         return;
     }
     this.error = ''

     await convert.ready();

     if (this.cryptoFirst == 'BTC' && this.cryptoSecond == 'ETH') 
          this.result =  convert.BTC.ETH(this.amount);

     if (this.cryptoFirst == 'BTC' && this.cryptoSecond == 'USDT') 
          this.result =  convert.BTC.USDT(this.amount);

     if (this.cryptoFirst == 'ETH' && this.cryptoSecond == 'BTC') 
          this.result =  convert.ETH.BTC(this.amount);

     if (this.cryptoFirst == 'ETH' && this.cryptoSecond == 'USDT') 
          this.result =  convert.ETH.USDT(this.amount);

     if (this.cryptoFirst == 'USDT' && this.cryptoSecond == 'BTC') 
          this.result =  convert.USDT.BTC(this.amount); 

     if (this.cryptoFirst == 'USDT' && this.cryptoSecond == 'ETH')  
          this.result =  convert.USDT.ETH(this.amount);     


     }

}
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
