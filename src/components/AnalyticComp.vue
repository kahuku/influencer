<template>
<div id="container">
    <div id="top-post">
        <div class="title">
            <h1>Top Post</h1>
        </div>
        <div class="image">
            <img :src="'/images/' + topPost.image">
        </div>
        <div class="metadata">
            <h2>Likes: {{Number(topPost.likes).toLocaleString("en-US")}}</h2>
            <h2>Comments: {{Number(topPost.comments).toLocaleString("en-US")}}</h2>
        </div>
    </div>
</div>
</template>

<script>
export default {
    name: 'AnalyticComp',
    props: {
        posts: Array,
    },
    computed: {
        topPost() {
            let topScore = 0;
            let topIndex = 0;
            for (let i = 0; i < this.posts.length; i++){
                let post = this.posts[i];
                let score = Number(post.likes) + Number(post.comments) * 2;
                if (score > topScore){
                    topScore = score;
                    topIndex = i;
                }
            }
            console.log(topIndex);
            return this.posts[topIndex]
        }
    }
}
</script>

<style scoped>
#container {
    display: flex;
    flex-direction: row;
}

#top-post {
  margin: 25px;
  width: 200px;
  box-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;
  background-color: #BBB;
}

.title h1 {
    margin: 0px;
    color: black;
}

img {
  width: 250px;
  width: 100%;
}

.image {
  display: flex;
  justify-content: center;
  width: fit-content;
  width: 100%;
  margin-bottom: 20px;
  border: 2px solid #FFF;
}

.metadata {
    color: black;
}

.h2 {
  padding: 0px;
  margin: 0px;
  font-weight: bolder;
}
</style>