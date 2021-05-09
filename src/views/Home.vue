<template>
  <div class="home">
    <h2>欢迎来到{{ userName }}的主页</h2>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data() {
    return {
      userName: "",
    };
  },
  mounted() {
    this.userName = this.$route.query.user;
  },
};
</script>
