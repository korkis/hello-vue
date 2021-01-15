<template>
  <div id="app">
    <div id="nav" v-if="!$route.meta.navigationHidden">
      <router-link to="/">Home</router-link> |
      <router-link :to="{ name : 'profile', params: { userId: 'abc' }}">Profile</router-link> |
      <router-link to="/about">About</router-link>
      <button @click="go">Click</button>
    </div>
    <router-view />
    <router-view name="a"/>
    <!-- <router-view name="b"/> -->
  </div>
</template>

<script>
export default {
  methods: {
    go() {
      this.$router.push({
        // path: '/profile/a',
        name: 'profile',
        params: {
          userId: 'abc'
        },
        query: {
          userId: 'abc',
          name: 'Hong'
        }
      });
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
