<template>
  <div>
    <AnalyticComp :posts="allPosts"/>
  </div>
</template>

<script>
import AnalyticComp from '../components/AnalyticComp.vue'
export default {
  name: 'AnalyticView',
  components: {
    AnalyticComp
  },
  computed: {
    allPosts() {
      return this.$root.$data.posts
    }
  }
}
</script>