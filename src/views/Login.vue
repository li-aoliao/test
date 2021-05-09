<template>
  <div class="login">
    <div class="content">
      <div class="user">
        <p>用户名:</p>
        <el-input v-model="user" placeholder="请输入用户名"></el-input>
      </div>
      <div class="password">
        <p>密码:</p>
        <el-input
          placeholder="请输入密码"
          v-model="password"
          show-password
        ></el-input>
      </div>
      <div class="btn">
        <el-button type="primary" @click="login">登录</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      user: "",
      password: "",
    };
  },
  methods: {
    login() {
      if (this.user !== "admin" && this.password !== "admin") {
        this.$router.push({
          path: "/error",
          query: {
            message: "用户名或密码错误",
          },
        });
      } else {
        this.$router.push({
          path: "/index",
          query: {
            user: "admin",
          },
        });
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.login {
  display: flex;
  .content {
    width: 600px;
    padding: 50px;
    border: 1px solid #eee;
    margin: 200px auto;
    .user-password {
      margin-bottom: 20px;
      display: flex;
      align-items: center;
      p {
        width: 100px;
        white-space: nowrap;
      }
      .el-input {
        width: 500px;
      }
    }
    .user {
      @extend .user-password;
    }
    .password {
      @extend .user-password;
    }
    .btn {
      margin-left: 100px;
    }
  }
}
</style>
