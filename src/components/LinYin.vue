<template>
  <div class="hello">
    <div class="left">
      <Left></Left>
    </div>
    <div class="right">
      <Right></Right>
    </div>
  </div>
</template>

<script>
  import Left from './pages/Left'
  import Right from './pages/Right'
    export default {
        name: "LinYin",
        components:{Left,Right},
        data () {
        return {
        }
      },
    }
</script>

<style scoped>
  .hello{
    position: relative;
    width: 100%;
    height: 100%;
    margin:0px;
    padding:0px;
    padding-top: 0;
    background-repeat: no-repeat;
    background-image:url('./../assets/bg1.png');
    background-size: 100% 100%;
  }
   .left{
     margin-left: 7%;
     margin-top: 29%;

     float: left;
     width: 800px;
     font-size: 80px;
     color: #ffffff;
   }
   .right{
     margin-right: 5.1%;
     margin-top: 21%;
     width: 40%;
     float: right;
   }
</style>
