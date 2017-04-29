<template>
  <div id="app">
    <transition name="slide-fade">
      <div v-if="display" class="box shadow">
        <div class="overlay"></div>
        <transition name="bounce" mode="out-in">
          <signup v-if="signup" @cancel="hideSignupForm"></signup>
          <login  v-else @signup="displaySignupForm"></login>
        </transition>
      </div>
    </transition>
  </div>
</template>

<script type="text/javascript">
import Login from './components/Login'
import Signup from './components/Signup'

export default {
  name: 'app',
  components: {
    Login,
    Signup
  },
  data () {
    return {
      login: true,
      signup: false,
      display: false
    }
  },
  created: function () {
    setTimeout(() => {
      this.display = true
    }, 100)
  },
  methods: {
    displaySignupForm: function () {
      this.signup = true
    },
    hideSignupForm: function () {
      this.signup = false
    }
  }
}
</script>

<style lang="scss" rel="stylesheet/scss">
@import 'assets/css/reset.css';
@import 'assets/css/box.scss';
@import 'assets/css/transition.scss';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
}
</style>
