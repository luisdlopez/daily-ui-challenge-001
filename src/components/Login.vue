<template>
  <form class="login">
    <input type="email" placeholder="E-mail"
            v-focus="focused" @focus="focused = true" @blur="focused = false">
    <input type="password" placeholder="Password">

    <button type="button" @click.prevent>Login</button>
    <a @click.prevent="signup">You don't have an account?</a>
  </form>
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
