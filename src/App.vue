<template>
  <div id="app">
    <transition name="slide-up">
      <div v-if="display" class="box shadow">
        <div class="overlay"></div>
        <transition :name="transition" mode="out-in">
          <component :is="view" @cancel="hideSignupForm" @signup="displaySignupForm"></component>
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
      display: false,
      view: '',
      transition: 'slide-right'
    }
  },
  created: function () {
    setTimeout(() => {
      this.display = true
    }, 100)
    setTimeout(() => {
      this.view = 'login'
    }, 400)
  },
  methods: {
    displaySignupForm: function () {
      this.view = 'signup'
      this.transition = 'slide-left'
    },
    hideSignupForm: function () {
      this.view = 'login'
      this.transition = 'slide-right'
    }
  }
}
</script>

<style lang="scss" rel="stylesheet/scss">
@import 'assets/css/reset.css';
@import 'assets/css/box.scss';
@import 'assets/css/transition.scss';

body {
  background-color: rgba(0, 0, 0, 0.06);
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  position: relative;
}
</style>
