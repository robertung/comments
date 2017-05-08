<template>
    <form class="form-horizontal" v-on:submit.prevent="onSubmit">
        <h4>Add your comment</h4>
        <div class="form-group">
          <label for="author" class="col-sm-2 control-label">Author</label>
          <div class="col-sm-10">
            <input id="author" type="text" class="form-control" placeholder="Name" v-model="author" />
          </div>
        </div>
        <div class="form-group">
          <label for="text" class="col-sm-2 control-label">Comment</label>
          <div class="col-sm-10">
            <input id="text" type="text" class="form-control" placeholder="Comment" v-model="text" />
          </div>
        </div>
          <input type="submit" class="btn btn-primary pull-right" value="submit"/>
        </div>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                author: "",
                text: "",
                timestamp: new Date()
            }
        },

        methods: {
            // Handle form submit
            onSubmit() {
                if (this.author != "" && this.text != "" && this.timestamp) {

                    // Dispatch event to parent components
                    this.$dispatch("new-comment", {
                        author: this.author,
                        text: this.text,
                        timestamp: this.timestamp

                    });
                    // Reset Form
                    this.author = "";
                    this.text = "";
                }
            }
        }
    };
</script>

<style>
form{
  margin:30px 0 0;
}
</style>
