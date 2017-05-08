<template>
    <ul>
        <comment v-for="comment in comments" :author="comment.author" :text="comment.text" :timestamp="comment.timestamp"></comment>
    </ul>
</template>

<script>
    import Comment from "./Comment.vue";

    export default {
        components: { Comment },
        props: ["comments"]
    };
</script>

<style>
    ul{
      margin:0;
      padding:0;
    }
    ul li{
      list-style:none;
      position:relative;
      padding:10px;
    }
    ul li:nth-of-type(odd){
      background:#f9f9f9;
    }
</style>
