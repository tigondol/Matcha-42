<template>
  <div class="overlay">
    <header v-if="$route.meta.title">
      <Navbar @loginClick="logIn"/>
    </header>
    <div className="home">
        <h1 className="primary-title">Swipe Right®</h1>
        <button class="primary-button" @click="createAccount">
          <p class="button-text">{{ authToken ? 'Signout ' : 'Create Account' }}</p>
        </button>
        <AuthModal v-if="showModal" :isSignUp="isSignUp" @closeModal="closeModal" />
    </div>
  </div>
</template>

<style lang="sass">
</style>

<script>
import Navbar from '../components/Navbar.vue'
import AuthModal from "../components/AuthModal.vue"

export default {
  name: 'Home',
  components: {
    Navbar,
    AuthModal,
  },
  data() {
    return {
      authToken: false,
      showModal: false,
      isSignUp: false,
    }
  },
  created() {
    console.log(this.authToken);
  },
  methods: {
    createAccount() {
      this.isSignUp = true;
      this.showModal = true
    },
    logIn() {
      this.isSignUp = false;
      this.showModal = true
    },
    closeModal() {
      this.showModal = false
    }
  }
};
</script>
