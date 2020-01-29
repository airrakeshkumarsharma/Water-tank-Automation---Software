<template>
  <div>
    <hero-bar>
      Settings
      <router-link slot="right" to="/" class="button">
        Dashboard
      </router-link>
    </hero-bar>
    <section class="section is-main-section">
      <tiles>
        <profile-update-form class="tile is-child"/>
      </tiles>
    </section>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import HeroBar from '@/components/HeroBar'
import ProfileUpdateForm from '@/components/ProfileUpdateForm'

export default {
  name: 'Profile',
  components: { ProfileUpdateForm, HeroBar },
  computed: {
    ...mapState([
      'userName',
      'userEmail'
    ])
  }
}
</script>
