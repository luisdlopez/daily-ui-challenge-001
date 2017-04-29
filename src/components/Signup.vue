<template>
  <div class="signup-container">
    <a @click.prevent="cancel" class="login-link">Already have an account?</a>
    <form class="signup-form">
      <input type="text" placeholder="Your Name" v-model="name" class="username"
              v-focus="focused" @focus="focused = true" @blur="focused = false">
      <input type="email" placeholder="E-mail" v-model="email" class="email">
      <input type="password" placeholder="Password"  v-model="password" class="password">
      <!-- <input type="password" placeholder="Password Confirmation" class="password-confirmation"
              v-model="passwordConfirmation"> -->

      <button type="button" @click.prevent class="join-button">Join</button>
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
