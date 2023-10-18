<script>
    import Card from "../components/Card.vue";
    import axios from "axios";

    export default{
        components:{
            Card,
        },
        data(){
            return{
                projects: [],
                pagination:{}
            }
        },
        methods: {

        // CHIAMATA AXIOS 
        getProjects() {
            axios.get("http://127.0.0.1:8000/api/projects")
                .then((response) => {
                    const result = response.data;
                    this.projects = result.data;
                    delete result.data;
                    this.pagination = result;
                    })
            },
        },

        mounted() {
            this.getProjects()
            }
        }
</script>

<template>
    <div class="content p-5">

    <div class="jumbotron p-5 mb-4 mt-5 rounded-3">
    <div class="container py-5 px-5">
        <div class="row align-items-center">
            <div class="col-12 col-lg-6 d-flex flex-column align-items-center justify-content-center gap-4">
                <h1 class="display-4 fw-bold text-center">
                    Welcome to my Portfolio
                </h1>
        
                <p class="fs-5 text-center lh-lg">Hello, I am Dario Esposito.</p>
            </div>
        </div>

    </div>
</div>

    <div class="container-fluid text-center p-5">
        <div class="row row-cols-3 mt-5 g-5 p-2" >
                <div class="col mt-5" v-for="project in projects">
                    <Card :singleCard="project"></Card>                   
                </div> 
        </div>
    </div>

    <div class="watch-more mt-5 text-center">
        <a href="" class="btn btn-primary more-button">WATCH MY PROJECTS</a>
    </div> 
</div> 
</template>

<style lang="scss" scoped>

</style>