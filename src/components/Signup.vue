<template>
  <div class="signup-container">

    <a @click.prevent="cancel" class="login-link">Already have an account?</a>
    <h1 class="title">Daily UI</h1>
    <p class="subtitle">Welcome!</p>

    <form class="signup-form">
      
      <div class="form-input">
        <i class="fa fa-user-circle" aria-hidden="true"></i>
        <input type="text" placeholder="Full Name" v-model="name" class="username"
              v-focus="focused" @focus="focused = true" @blur="focused = false">
      </div>
      
      <div class="form-input">
        <i class="fa fa-envelope" aria-hidden="true"></i>
        <input type="email" placeholder="E-mail Address" class="email">
      </div>

      <div class="form-input">
        <i class="fa fa-lock" aria-hidden="true"></i>
        <input type="password" placeholder="Password" class="password">
      </div>

      <button type="button" @click.prevent class="join-button">SIGN UP</button>
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
      email: '',
      name: '',
      password: '',
      passwordConfirmation: ''
    }
  },
  methods: {
    cancel: function () {
      this.$emit('cancel')
    }
  }
}
</script>

<style lang="scss" rel="stylesheet/scss">
@import '../assets/css/forms.scss';
</style>
