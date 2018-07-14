<template>
  <div class="yangshi">
    <vue-seamless-scroll :data="newsList" :class-option="optionLeft" class="seamless-warp2">
      <ul class="item">
        <li v-for="item in newsList" v-text="item.title"></li>
      </ul>
    </vue-seamless-scroll>
  </div>

</template>
<script>
  export default {
    data () {
      return {
        newsList: [
          {
            'title': '兰轩村庄食坊 预约电话：0571-12345678'
          },
          {
            'title': '杭州法云安缦 在线订房热线：0571-12345678'
          },
        ]
      }
    },
    computed: {
      optionLeft () {
        return {
          direction: 2,
          limitMoveNum: 1
        }
      }
    }
  }
</script>
<style lang="scss" scoped>
  .yangshi{
    margin-left:50%;
    height:100%;
  }
  .seamless-warp2 {
    overflow: hidden;

    /*这个height是控制显示屏幕的高度，删除了之后就是全屏*/

    margin-left: -60%;

    width: 700px;
    ul.item {
      width: 1900px;
      li {
        float: left;
        margin-right: 10px;
        margin-top:10px ;
        list-style:none;
      }
    }
  }
</style>
