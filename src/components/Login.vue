<template>
  <div class="login-container">
    
    <a @click.prevent="signup" class="signup-link">You don't have an account?</a>
    <h1 class="title">Daily UI</h1>
    <p class="subtitle">Welcome back!</p>

    <form class="login-form">

      <div class="form-input">
        <i class="fa fa-envelope" aria-hidden="true"></i>
        <input type="email" placeholder="E-mail Address" class="email"
                v-focus="focused" @focus="focused = true" @blur="focused = false">
      </div>

      <div class="form-input">
        <i class="fa fa-lock" aria-hidden="true"></i>
        <input type="password" placeholder="Password" class="password">
      </div>

      <button type="button" @click.prevent class="login-button">SIGN IN</button>

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
