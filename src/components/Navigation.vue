<template>
  <div class="navigation">
    <div class="box" :style="boxWidth">
      <div class="left">
        <i :class="iconVisible==true?'iconfont iconshang':'iconfont iconxia'" @click="popUp" ></i>
        <p class="ml10">oneMan</p>
      </div>
      <i class="iconfont iconjia add" v-show="iconVisible"></i>
      <div class="right" v-show="iconVisible">
        <i class="iconfont iconsousuo" @click="no('搜索功能暂未开放哟~')"></i>
        <i class="iconfont icondiandian" @click="no('更多功能暂未开放哟~')"></i>
      </div>
      
    </div>
    <!--弹窗-->
    <mt-popup
      v-model="popupVisible"
      position="bottom"
      :closeOnClickModal="closeOnClickModal"
      >
      <div>
        <div class="modalHead">
           <div class="left" ></div>
           <div class="right">
             <p>小眼睛李荣浩</p>
             <span>一句话描述</span>
           </div>
        </div>
        <mt-cell title="文章">
          <span>10</span>
          <img slot="icon" src="../assets/wenzhang.png" width="24" height="24">
        </mt-cell>
        <mt-cell title="收藏">
          <span>10</span>
          <img slot="icon" src="../assets/shoucang.png" width="24" height="24">
        </mt-cell>
        <mt-cell title="位置">
          <span>10</span>
          <img slot="icon" src="../assets/dingwei.png" width="24" height="24">
        </mt-cell>
        
      </div>
    </mt-popup>
  </div>
</template>

<script>

export default {
  name: 'Navigation',
  data () {
    return {
      iconVisible: true,
      popupVisible:false,//弹窗
      closeOnClickModal:false,
      boxWidth:{width:"100%"},
  
      
    }
  },
  methods:{
    popUp(){
      if(this.iconVisible==true){
        this.iconVisible=false;
        this.popupVisible=true;
        this.boxWidth={width:"50%"}
      }else{
        this.iconVisible=true;
        this.popupVisible=false;
        this.boxWidth={width:"100%"}
      }
    },
    no(text){
      this.$toast({
        message: text,
        duration: 1500
      })
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
    z-index: 5000;
    position: relative;
    border-radius: 0px 10px 0px 0px;
    transition: width 1s;
    .left{
      display: flex;
      align-items: center;
      padding-left: 10px;
      width: 30%;
    }
    .right{
      margin-right: 10px;
      width: 30%;
      text-align: end;
    }
    .add{
      font-size: 40px;
      margin-top: -24px;
    }
  }
  .ml10{margin-left: 10px;}
  .modalHead{
    display: flex;
    align-items: center;
    padding: 10px 0;
    .left{
      width: 45px;
      height: 45px;
      background: red;
      border-radius: 100%;
      margin: 0 10px;
      background:url("../assets/head.jpg") no-repeat;
      background-size: 100%;
    }
    .right{
      p{
        font-size: 16px
      }
      span{
        font-size: 14px;
      }
      
    }
  }
  .mint-popup{
    width: 100%;
    padding-bottom: 80px;
    border-radius: 10px 10px 0 0
  }
}
</style>
