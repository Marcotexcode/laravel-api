


<template>
  
    <div class="container">

        <div class="row">
       
            <div class="col-sm-6" v-for="post in posts" :key="post.id">
       
                <div class="card m-3">
       
                    <div class="card-body">
        
                        <h5 class="card-title">{{post.title}}</h5>
        
                        <p class="card-text">{{post.content}}</p>
        
                        <a href="#" class="btn btn-primary">Go somewhere</a>
        
                    </div>
       
                </div>
       
            </div>
       
       
        </div>
         
    </div>

</template>


<script>

    export default {

        name: 'Main',

        data() {

            return {

                chiamataApi: 'http://localhost:8000/api/posts',

                posts: []

            }

        },

        created() {

            this.getPosts();

        },

        methods: {

            getPosts() {

                axios.get(this.chiamataApi)

                     .then(response => {
                         
                        this.posts = response.data.result;
                     })

                     .catch();

            }

        }

    }

</script>


<style lang="scss" scoped>


</style>