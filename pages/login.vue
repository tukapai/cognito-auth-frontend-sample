<template>
  <form>
    <input type="text" v-model="username" placeholder="Username" required autofocus>
    <input type="password" v-model="password" placeholder="Password" required>
    <button @click.prevent="signIn">Sign in</button>
  </form>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      username: '',
      password: '',
    }
  },
  methods: {
    async signIn() {
      try {
        const { username, password } = this
        await this.$auth.loginWith('cognito', {
          data: {
            username,
            password,
          }
        })
      } catch (error) {
        console.error(error)
      }
    }
  }
}
</script>

<style scoped>

</style>
