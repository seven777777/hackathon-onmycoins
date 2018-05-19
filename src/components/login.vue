<template>
  <div class="login_wrap">
    <div class="login_box">
      <p class="title">Oh My Coins</p>
      <div class="line">
        <div class="label">自定义币种:</div>
        <input type="text" v-model="other_bl">
      </div>
      <div class="line">
        <div class="label">地址:</div>
        <input type="text" v-model="addresses">
      </div>
      <div class="cutline">通过交易所API查询余额</div>
      <div class="line">
        <div class="label">bittrex apikey:</div>
        <input type="text" v-model="bittrex_apikey">
      </div>
      <div class="line">
        <div class="label">bittrex apisecret:</div>
        <input type="text" v-model="bittrex_apisecret">
      </div>
      <div class="line">
        <div class="label">poloniex apikey:</div>
        <input type="text" v-model="poloniex_apikey">
      </div>
      <div class="line">
        <div class="label">poloniex apisecret:</div>
        <input type="text" v-model="poloniex_apisecret">
      </div>
      <div class="line">
        <div class="label">bitfinex apikey:</div>
        <input type="text" v-model="bitfinex_apikey">
      </div>
      <div class="line">
        <div class="label">bitfinex apisecret:</div>
        <input type="text" v-model="bitfinex_apisecret">
      </div>
      <div class="line">
        <div class="label">bigone apikey:</div>
        <input type="text" v-model="bigone_apikey">
      </div>
      <div class="line">
        <div class="btn" @click="getData">走你!~</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      //自定义币种
      other_bl: '',
      //地址
      addresses: '',
      //通过交易所API查询余额
      bittrex_apikey: '',
      bittrex_apisecret: '',
      poloniex_apikey: '',
      poloniex_apisecret: '',
      bitfinex_apikey: '',
      bitfinex_apisecret: '',
      bigone_apikey: '',
      param:{},
    }
  },
  methods:{
    setParame(){
      
    },
    getData(){
      console.log('click');
      $.post("http://192.168.0.87:5050",{test:'test'},function(result){
        console.log(result);
      });
    },
    goHome(){
      this.$router.push({path:'/home'});
    }
  }
}
</script>

<style lang="scss">
.login_wrap{
  width: 100%;
  .login_box{
    width: 550px;
    margin: 0 auto;
    margin-top: 60px;
    background: rgba(255,255,255, .6);
    padding: 20px;
    border-radius: 6px;
    box-sizing: border-box;
    .title{
      text-align: center;
      font-size: 24px;
      margin: 15px auto;
    }
    .cutline{
      height: 30px;
      margin: 20px auto;
      font-size: 16px;
      color: #5e5e5e;
      line-height: 30px;
      text-align: center;
      background: url('../assets/cutline.png') center center no-repeat;
    }
    .line{
      width: 100%;
      height: 36px;
      margin-bottom: 10px;
      &:last-child{
        margin-top: 30px;
      }
      .label{
        width: 25%;
        display: inline-block;
        text-align: right;
        line-height: 36px;
        font-size: 14px;
        margin-right: 15px;
      }
      input{
        width: 70%;
        height: 36px;
        border: none;
        border-radius: 3px;
      }
      .btn{
        width: 100px;
        height: 36px;
        background: #59718a;
        text-align: center;
        line-height: 36px;
        font-size: 16px;
        margin: 0 auto;
        border-radius: 6px;
        color: white;
        cursor: pointer;
      }
    }
  }
}
</style>
