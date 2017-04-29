<template>
  <form class="signup">
    <input type="text" placeholder="Your Name" v-model="name"
            v-focus="focused" @focus="focused = true" @blur="focused = false">
    <input type="email" placeholder="E-mail" v-model="email">
    <input type="password" placeholder="Password"  v-model="password">
    <input type="password" placeholder="Password Confirmation" v-model="passwordConfirmation">

    <button type="button" @click.prevent="cancel">Back</button>
    <button type="button" @click.prevent>Join</button>
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
