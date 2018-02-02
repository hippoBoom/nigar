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
          <p>验证码：</p>
          <p>{{randomNum}}</p>
          <input v-model="fakeCode" type="text" class="form-control" placeholder="快点好嘛这题没难度的">
        </div>
      </form>

      <div class="tool-tip">
        哈哈哈哈哈哈哈哈，善良的你，不要再算了跳过这个！
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
        let a = Math.random() * 1000 + 41000
        let b = Math.random() * 1000 + 1
        let c = Math.random() * 20 + 1
        let d = Math.random() * 500 + 1
        return `${parseInt(a)}*${parseInt(b)}/${parseInt(c)}*${parseInt(d)}`
      }
    },
    methods: {
      verification() {
        if (!this.fakeCode) {

        } else {

        }
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
        background: aqua;
        position: absolute;
        left: 25px;
        bottom: 0px;
        padding: 10px;
      }
    }
  }


</style>
