<script>
    export default{
        props:{
            singleCard: Object
        },
        methods:{

        getImg(singleCard){
            return `http://127.0.0.1:8000/storage/${singleCard.thumb}`
            }
        }
    }
</script>

<template>
        <div class="card proj-card" :key="singleCard.id">
            <img :src="getImg(singleCard)" class="card-img-top" alt="">
            <div class="card-body d-flex flex-column">
                <h5 class="card-title">{{singleCard.title}}</h5>
                <router-link :to="{ name: 'project.show', params: { slug: singleCard.slug}}" class="btn btn-primary">Dettagli</router-link>
            </div>
        </div>
</template>

<style lang="scss" scoped>

</style>