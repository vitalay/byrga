
<template>
    
      <ul>
        <li @click="selectItem('BTC')" :className="current == 'BTC' ? 'active' : ''">Bitcoin</li>
        <li @click="selectItem('ETH')" :className="current == 'ETH' ? 'active' : ''">ETH</li>
        <li @click="selectItem('USDT')" :className="current == 'USDT' ? 'active' : ''">USDT</li>
        
      </ul>
    </template>
    
    
    <script>
    
    export default {
        props: {
            setCrypto: {
                type: Function,
                required: true
            }
        },
        data() {
            return {
               current: ''       
            }
        },
        methods: {
               selectItem(val) {
                   this.setCrypto(val);
                   this.current = val
                   
               }            
                  
        }
        
    }
    
    </script>
    
    <style scoped>
    ul {
        list-style-type: none;
        width: 200px;
        padding: 0;
        border-radius: 3px;
        border: 3px solid #000;
    }
    
    li {
        display: block;
        padding: 20px 0;
        color: #fff;
        background: #234bb8;
    }
    
    li:hover, li.active {
        background: #0b2150;
        cursor: pointer;
    }
    </style>