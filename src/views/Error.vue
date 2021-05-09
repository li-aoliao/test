<template>
  <div class="error">
    <h2>{{ errorMsg }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      errorMsg: "",
    };
  },
  mounted() {
    this.errorMsg = this.$route.query.message;
  },
};
</script>

<style lang="scss" scoped>
</style>