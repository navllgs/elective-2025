<!-- html -->
<template>
  <div>
    <input type="text" v-model="email" placeholder="Email" />
    <input type="password" v-model="password" placeholder="Password" />
    <button @click="login()">Login</button>
    <div>
      Email: {{ email }}
    </div>
    <div>
      Password: {{ password }}
    </div>
  </div>
</template>

<!-- javascript -->
<script>
export default {
  props: {
    title: {
      type: String,
      default: "Form"
    }
  },

  data() {
    return {
      email: "",
      password: ""
    };
  },

  methods: {
    login(){
      alert(`${this.email}---${this.password}`)
    }
  }
}
</script>

<!-- css style -->
<style>

</style>