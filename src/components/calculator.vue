<template>
  <div class="calculator">
    <div class="display">{{current||0}}</div>
    <div @click="clear" class="btn">Clear</div>
    <div @click="sign" class="btn">+/-</div>
    <div @click="percent" class="btn">%</div>
    <div class="btn operator">/</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('7')" class="btn">7</div>
    <div class="btn operator">+</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('4')" class="btn">4</div>
    <div class="btn operator">x</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('1')" class="btn">1</div>
    <div class="btn operator">-</div>
    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot" class="btn">.</div>
    <div class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  name: 'calculator',
 data(){
   return{
     current:''
     
   }
 },
 methods:{
   clear(){
     this.current='';   
     },
     sign(){
       this.current=this.current.charAt(0)==='-'?
       this.current.slice(1):`-${this.current}`;
     },
     percent(){
       this.current=`${parseFloat(this.current)/100}`;
     },
     append(number){
       this.current=`${this.current}${number}`
     },
     dot(){
       if(this.current.indexOf('.') === -1)
       {
          this.append('.');
       }else {
         this.current=`error`
       }
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