<template>
  <div class="comment-box">
    <h1>Comments</h1>
    <comment-list :comments="comments"></comment-list>
    <comment-form></comment-form>
  </div>
</template>

<script>
    import CommentList from "./CommentList.vue";
    import CommentForm from "./CommentForm.vue";

    export default {
        components: { CommentList, CommentForm },
        data () {
            return {
                comments: [
                    {
                      author: "Robert",
                      text: "Comments are now working.",
                      timestamp: "Sun May 07 2017 20:48:03 GMT-0700 (PDT)"
                    }
                ]
            }
        },

        events: {
            // Add new comment
            "new-comment": function(comment) {
                this.comments.push(comment);
            }
        }
    }
</script>

<style>
    .comment-box {
        max-width: 960px;
        margin: 0 auto;
    }
</style>
