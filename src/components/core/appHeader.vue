<template>
  <div id="nav">
    <router-link :to="{ name: 'Home' }">Home</router-link> |
    <router-link :to="{ name: 'About' }">About</router-link>
  </div>
  {{ text }}
</template>
<script>
import { watchEffect } from "vue";
export default {
  name: "appHeader",
  props: {
    text: String
  },
  setup(props) {
    watchEffect(() =>
      console.log("watchEffect props from setup function: ", props.text)
    );
  }
};
</script>
<style lang="scss">
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
