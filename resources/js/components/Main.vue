<template>
    <div class="container">
        <div class="card" v-for="(post, index) in posts" :key="index">
            <img src="" class="card-img-top" alt="">
            <div class="card-body">
                <h5 class="card-title">{{post.title}}</h5>
                <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
        </div>
        <nav>
            <ul class="pagination">
                <li class="page-item" :class="(currentPage==1?'disabled':'')" ><a class="page-link" href="#" @click.prevent="getPosts(currentPage - 1)">Previous</a></li>
                <li class="page-item" :class="(currentPage==lastPage)?'disabled':''"><a class="page-link" href="#" @click.prevent="getPosts(currentPage + 1)">Next</a></li>
            </ul>

        </nav>
    </div>
</template>

<script>

export default {
    name:"Main",
    data(){
        return{
            posts:[],
            currentPage: 1,
            lastPage: null,

        }
    },
    methods: {
        getPosts(page) {
                axios.get('/api/posts', {
                    params: {
                        page: page
                    }
                })
                .then((response) => {
                    this.posts = response.results.data;
                    this.currentPage = response.results.data.current_page;
                    this.lastPage = response.results.data.last_page;
                });
            }
    }
}
</script>

<style>

</style>