
<template>
    
      <ul>
        <li>Bitcoin</li>
        <li>ETH</li>
        <li>USDT</li>
      </ul>
    </template>
    
    
    <script>
    
    export default {
        
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