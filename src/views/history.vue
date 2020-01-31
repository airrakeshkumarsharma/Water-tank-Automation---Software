<template>
  <div>
    <hero-bar>
      History
      <router-link slot="right" to="/" class="button">
        Dashboard
      </router-link>
    </hero-bar>
    <section class="section is-main-section">
      <card-component class="has-table has-mobile-sort-spaced" title="Water Uses Report" icon="account-multiple">
        <clients-table-sample data-url="/data-sources/clients.json" :checkable="true"/>
      </card-component>

      <hr>

    </section>
  </div>

</template>

<script>
import ClientsTableSample from '@/components/ClientsTableSample'
import CardComponent from '@/components/CardComponent'
import HeroBar from '@/components/HeroBar'
export default {
  name: 'History',
  components: { HeroBar, CardComponent, ClientsTableSample },
  computed: {
    titleStack () {
      return [
        'Admin',
        'Tables'
      ]
    }
  }
}
</script>
