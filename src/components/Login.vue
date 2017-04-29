<template>
  <div class="login-container">
    <a @click.prevent="signup" class="signup-link">You don't have an account?</a>
    <form class="login-form">
      <input type="email" placeholder="E-mail" class="email"
              v-focus="focused" @focus="focused = true" @blur="focused = false">
      <input type="password" placeholder="Password" class="password">

      <button type="button" @click.prevent class="login-button">Login</button>
    </form>

  </div>
</template>

<script>
import { focus } from 'vue-focus'

export default {
  name: 'login',
  directives: {
    focus
  },
  data () {
    return {
      focused: true,
      username: '',
      password: ''
    }
  },
  methods: {
    signup: function () {
      this.$emit('signup')
    }
  }
}
</script>

<style lang="scss" rel="stylesheet/scss">
@import '../assets/css/forms.scss';
</style>
