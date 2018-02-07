<template>
  <div class="login-box">
    <div class="login">
      <form>
        <div class="form-group">
          <p>芳名：</p>
          <input type="text" class="form-control" placeholder="名字应该很好听">
        </div>
        <div class="form-group">
          <p>密码：</p>
          <input type="password" class="form-control" placeholder="看看后面有人吗">
        </div>
        <div class="form-group">
          <p>破解暗号：</p>
          <p>{{randomNum}}</p>
          <input v-model="fakeCode" type="text" class="form-control" placeholder="答对有彩蛋哦！">
        </div>
      </form>

      <div class="tool-tip">
        如果没破解出来这个不用填,不过填对了有彩蛋！！！
        <span></span>
      </div>

      <button @click="verification()" type="button" class="btn btn-primary btn-lg btn-block">开车了</button>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        fakeCode: ''
      }
    },
    computed: {
      randomNum() {
        return `%E6%88%91%E5%96%9C%E6%AC%A2%E4%BD%A0`
      }
    },
    methods: {
      verification() {
        let params={
          userName :'hippo',
          userPwd:'hippo537'
        }
        this.$axios.post('/users/login',params).then((response)=>{
          let res=response.data
          // if(res.status)
        })


        // if (!this.fakeCode) {
        //
        // } else {
        //
        // }
      }
    }
  }
</script>

<style scoped lang="scss">
  @import "../style/common";

  .login-box {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
    background: $bgc-pink;
    .login {
      background: $bgc;
      max-width: 400px;
      padding: 25px;
      border-radius: 8px;
      position: relative;
      .tool-tip {
        width: 221px;
        background: rgba(229,185,199,0.9);
        color: #ffffff;
        position: absolute;
        left: 25px;
        bottom: 135px;
        padding: 10px;
        word-wrap: break-word;
        border-radius: 5px;
        span{
          width: 0;
          height: 0;
          border-top: 7px solid rgba(229,185,199,0.9);
          border-left: 7px solid transparent;
          border-right: 7px solid transparent;
          transform: translate(-50%,-50%);
          position: absolute;
          bottom: -10px;
          left: 50%;
        }
      }
      .form-group{
        max-width: 221px;
        word-wrap: break-word;
      }
    }
  }


</style>
