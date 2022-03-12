<template>
  <div>
    <IncomeComp :sponsors="this.$root.$data.sponsorships" :affiliate="this.$root.$data.affiliate" />
  </div>
</template>

<script>
import IncomeComp from '../components/IncomeComp.vue'
export default {
  name: 'IncomeView',
  components: {
    IncomeComp
  }
}
</script>