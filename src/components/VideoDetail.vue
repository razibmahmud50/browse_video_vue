<template>
   <div v-if="video" class="col-md-8">
        <div class="video-details">
            <div class="embed-responsive embed-responsive-16by9">
                <iframe class="embed-responsive-item" :src="videoUrl"></iframe>
            </div>
           <h3 class="title">{{video.snippet.title}}</h3>
           <p class="description">{{video.snippet.description}}</p>
        </div>
   </div>
</template>
<script>
export default {
    name:"VideoDetail",
    props:['video'],
    computed:{
        videoUrl(){
            const videoId = this.video.id.videoId
            return `https://www.youtube.com/embed/${videoId}`
        }
    }
}
</script>
<style scoped>
.video-details{
    padding: 8px;
    border: 1px solid #ddd;
}
</style>