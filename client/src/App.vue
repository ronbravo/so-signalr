<template>
  <div id="app">
    <main-navbar />

    <main role="main" class="container mt-4">
      <router-view/>
    </main>

    <login-modal />
    <live-chat-modal />
  </div>
</template>

<script>
import { mapActions } from 'vuex'
import MainNavbar from './components/main-navbar.vue'
import LoginModal from './components/login-modal.vue'
import LiveChatModal from '@/components/live-chat-modal.vue'

export default {
  name: 'App',
  components: {
    MainNavbar,
    LoginModal,
    LiveChatModal
  },
  created () {
    this.restoreContext()
  },
  methods: {
    ...mapActions('context', [
      'restoreContext'
    ])
  }
}
</script>
