<template>
  <div class="calculator">
    <div class="display">{{current||0}}</div>
    <div @click="clear" class="btn">Clear</div>
    <div class="btn">+/-</div>
    <div class="btn">%</div>
    <div class="btn operator">/</div>
    <div class="btn">9</div>
    <div class="btn">8</div>
    <div class="btn">7</div>
    <div class="btn operator">+</div>
    <div class="btn">6</div>
    <div class="btn">5</div>
    <div class="btn">4</div>
    <div class="btn operator">x</div>
    <div class="btn">3</div>
    <div class="btn">2</div>
    <div class="btn">1</div>
    <div class="btn operator">-</div>
    <div class="btn zero">0</div>
    <div class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: 'calculator',
 data(){
   return{
     current:'12324'
   }
 },
 methods:{
   clear(){
     this.current='';   
     }
 }
  
}
</script>


<style scoped>
   .calculator{
     display: grid;
     grid-template-columns: repeat(4,1fr);
     grid-auto-rows: minmax(50px,auto);
     font-size:30px;
     width:50%;
     margin: 0 auto;
     
   }
   .display{
     grid-column: 1/5;
     background-color: aquamarine;
     font-size: 50px;
     text-align: center;
   }
   .zero{
      grid-column: 1/3;
   } 

   .btn{
     background-color: darkturquoise;
     border: 1px solid floralwhite;
     text-align: center;
     
   }

  .operator{
    background-color: dimgrey;
    color: gold;
  }

</style>
