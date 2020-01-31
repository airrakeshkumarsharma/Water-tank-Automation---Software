<template>
  <card-component title="Change Settings" icon="settings">
    <form @submit.prevent="submit">
      <b-field horizontal label="Automatic Mode">
        <b-switch v-model="form.mode" name="mode"/>
      </b-field>
      <b-field horizontal label="Motor Controller">
        <b-switch v-model="form.motor" name="motor"/>
      </b-field>
      <hr>
      <b-field horizontal>
        <div class="control">
          <button type="submit" class="button is-primary" :class="{'is-loading':isLoading}">
            Submit
          </button>
        </div>
      </b-field>
    </form>
  </card-component>
</template>

<script>
import { mapState } from 'vuex'
import CardComponent from '@/components/CardComponent'

export default {
  name: 'changeSettings',
  components: {
    CardComponent
  },
  data () {
    return {
      isLoading: false,
      form: {
        mode: null
      }
    }
  },
  computed: {
    ...mapState([
      'automaticMode'
    ])
  },
  mounted () {
    this.form.mode = this.mode
    console.log(this.form.mode)
  },
  methods: {
    submit () {
      this.isLoading = true
      setTimeout(() => {
        this.isLoading = false
        this.$store.commit('user', this.form)
        this.$buefy.snackbar.open({
          message: 'Updated',
          queue: false
        })
      }, 500)
    }
  },
  watch: {
    automaticMode (newValue) {
      this.form.mode = newValue
    }
  }
}
</script>
