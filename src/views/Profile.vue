<template>
  <div>
    <h3>My Profile</h3>
    <h4>{{ $route.params.userId }}</h4>
    <h4>{{ $route.params.name }}</h4>
    <h4>{{ $route.query.name}}</h4>
    <h4>{{ p }} </h4>
  </div>
</template>

<script>
export default {
  created() {
    // console.log(this.$router);
    // alert(this.$route.query.name);
    console.log(process.env.VUE_APP_NOT_SECRET_CODE);
  },
  data() {
    return {
      p: process.env.VUE_APP_NOT_SECRET_CODE
    };
  }
}
</script>

<style>

</style>