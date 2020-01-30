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
        <change-settings class="tile is-child"/>
      </tiles>
    </section>
  </div>
</template>

<script>
import { mapState } from 'vuex'
import HeroBar from '@/components/HeroBar'
import Tiles from '@/components/Tiles'
import changeSettings from '@/components/changeSettings'

export default {
  name: 'settings',
  components: { changeSettings, HeroBar, Tiles },
  data () {
    return {
      mode: false
    }
  },
  computed: {
    ...mapState([
      'mode'
    ])
  }
}
</script>
