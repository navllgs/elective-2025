<script>
import Box from "./components/Box.vue";
import Form from "./components/Form.vue";

export default {
  components: {
    Box, Form
  },

  data() {
    return {
      navigation: [
        { text: "Home", path: "/" },
        { text: "Calendar", path: "/calendar" },
        { text: "About", path: "/about" },
        { text: "Login", path: "/login" },
      ]
    };
  },

  methods: {
    goTo(path) {
      // page routing
      this.$router.push(path);
    }
  }
};
</script>

<template>
  <div style="width: 100%; height: 100vh; position: relative; ">

    <header style="position: fixed; top: 0; left: 0; right: 0; background-color: aqua;">
      header
    </header>

    <div style="display: flex; margin-bottom: 60px; margin-top: 60px;">

      <nav style="width: 200px; background-color: bisque;">

        <div @click="goTo(route.path)" class="pointer" style="margin: 20px 10px; background-color: #eee; padding: 10px;"
          v-for="route, i in navigation" :key="i">
          {{ route.text }}</div>

      </nav>

      <div style="flex-grow: 1; background-color: #fff; overflow-y: auto; height: calc(100vh - 120px); padding: 10px;">
        <RouterView></RouterView>
      </div>

    </div>

    <footer style="position: fixed; bottom: 0; left: 0; right: 0; background-color: cadetblue;">
      footer
    </footer>

  </div>
</template>

<style scoped>
header,
footer {
  line-height: 1.5;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.pointer {
  cursor: pointer;
}
</style>
