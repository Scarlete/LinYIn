<template>
  <div class="vueBox">
    <div class="tour-right">
      <div class="right-number" >
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[0]}}</span>
        <i class="kong"></i>
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[1]}}</span>
        <i class="kongg"></i>
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[2]}}</span>
        <i class="kongge"></i>
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[3]}}</span>
        <i class="konggel"></i>
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[4]}}</span>
        <i class="konggel"></i>
        <span :class="{'three':isThree,'two':isTwo,'one':isOne}">{{myNumber[5]}}</span>
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'HelloWorld',
    data(){
      return{
        tempData:[],
        myNumber:"00000000",
        isThree:false,
        isTwo:false,
        isOne:false,
      }
    },

    created: function () {
      this.getNumber();
      this.changeColor();
    },
    methods: {
      async getNumber() {
        // const personData = await touristNumber();
        const personData = [
          "009974","004568","004568",
          "002271","002265","002262",
          "012263","012265","112262",
          "012211","112265","112261",
          "102260","102265","102268"
        ];
        personData ? this.solveData(personData) : null;
      },
      solveData(val) {
        for(let i=0; i < val.length;i++) {
//                this.tempData.push(val[i].countNumber);
          this.tempData.push(val[i]);
        }
//            console.log(this.tempData);
        setInterval(this.changeNumber, 1000);

      },

      roundNumber() {
        return Math.round(Math.random()*14);
      },
      changeNumber() {
        this.myNumber = this.tempData[this.roundNumber()];
        this.changeColor()
      },
      changeColor(){
        if( this.myNumber<10000){
          this.isOne=true;
          this.isTwo=false;
          this.isThree=false;
        }else if(this.myNumber>10000&&this.myNumber<100000){
          this.isOne=false;
          this.isTwo=true;
          this.isThree=false;
        }else {
          console.log(this.myNumber);
          this.isTwo=false;
          this.isOne=false;
          this.isThree=true;
        }
      }
    },


  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>




  .kongge{

    margin-right: 10%;
  }
  .konggel{
    margin-right: 0.4%;
  }
  .kongg{
    margin-right: 0.4%;
  }
  .kong{
    margin-right: 0.3%;
  }
  .one{
    font-size: 100px;
    background-color: red;

    margin-left: 3.8%;
    margin-right: 2.1%;
  }
  .two{
    font-size: 100px;
    background-color: yellow;

    margin-left: 3.8%;
    margin-right: 2.1%;
  }
  .three{
    font-size: 100px;
    background-color: green;

    margin-left: 3.8%;
    margin-right: 2.1%;
  }


</style>
