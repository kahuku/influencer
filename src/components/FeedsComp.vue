<template>
<div>
  <div id="feeds">
    <FeedComp :posts="postsSnap" :platform="snap" class="feed"/>
    <FeedComp :posts="postsInsta" :platform="insta" class="feed"/>
    <FeedComp :posts="postsTikTok" :platform="tiktok" class="feed"/>
    <FeedComp :posts="postsTwitter" :platform="twitter" class="feed"/>
  </div>
</div>
</template>

<script>
import FeedComp from './FeedComp.vue'
export default {
  name: 'FeedsComp',
  components: {
    FeedComp
  },
  computed: {
    postsSnap() {
      return this.$root.$data.posts.filter(post => post.platform === "Snapchat")
    },
    postsInsta() {
      return this.$root.$data.posts.filter(post => post.platform === "Instagram")
    },
    postsTikTok() {
      return this.$root.$data.posts.filter(post => post.platform === "TikTok")
    },
    postsTwitter() {
      return this.$root.$data.posts.filter(post => post.platform === "Twitter")
    },
    insta() {
      return 'Instagram'
    },
    snap() {
      return 'Snapchat'
    },
    tiktok() {
      return 'TikTok'
    },
    twitter() {
      return 'Twitter'
    }
  }
}
</script>

<style scoped>
#feeds {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
}

.feed {
  width: 25%;
}

@media only screen and (max-width: 768px) {
  #feeds {
    flex-direction: column;
    justify-items: center;
  }

  .feed {
    width: 80%;
  }
}
</style>