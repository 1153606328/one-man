<template>
  <div class="navigation">
    <div class="box" :style="boxWidth">
      <div class="left">
        <i :class="iconShow==true?'iconfont iconshang':'iconfont iconxia'" @click="popUp" ></i>
        <p class="ml10">oneMan</p>
      </div>
      <div class="right" v-show="iconShow">
        <i class="iconfont iconsousuo"></i>
        <i class="iconfont icondiandian"></i>
      </div>
    </div>
    <!-- <mt-actionsheet
  :actions="arr"
  v-model="iconShow">
</mt-actionsheet> -->
  </div>
</template>

<script>

export default {
  name: 'Navigation',
  data () {
    return {
      iconShow: true,
      boxWidth:{width:"100%"},
      arr:[
          {name:"1",method:()=>console.log("1")},
          {name:"2",method:()=>console.log("2")}
      ]
    }
  },
  methods:{
    popUp(){
      if(this.iconShow==true){
        this.iconShow=false;
        this.boxWidth={width:"50%"}
      }else{
        this.iconShow=true;
        this.boxWidth={width:"100%"}
      }
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.navigation{
  position: absolute;
  bottom: 0;
  width: 100%;
  .box{
    background: #ffcdd2;
    height: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: width 1s;
    .left{
      display: flex;
      align-items: center;
      padding-left: 10px;
    }
    .right{
      margin-right: 10px;
    }
  }
  .ml10{margin-left: 10px;}
}
</style>
