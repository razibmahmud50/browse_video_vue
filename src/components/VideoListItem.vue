<template>
       <li class="list-group-item media d-flex" @click="onSelectVideo">
           <img class="mr-3" 
           :src="thumbnailUrl"
            alt="video Img">
           <div class="media-body">
              {{video.snippet.title}}
           </div>
       </li>
</template>
<script>
export default {
    name:'VideoListItem',
    props:['video'],
    computed:{
        thumbnailUrl(){
            return this.video.snippet.thumbnails.default.url;
        }
    },
    methods:{
        onSelectVideo(){
            this.$emit('videoSelect', this.video)
        }
    }
}
</script>
<style scoped>
.list-group-item{
    cursor: pointer;
}
.list-group-item:hover{
    background: #eee;
}
</style>