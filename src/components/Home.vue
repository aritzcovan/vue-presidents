<template>
    <div class="container">
        <section class="header">
            <nav class="navbar">
                <div class="navbar-brand">
                    <a class="navbar-item" href="#">
                    <img src="presidentSeal.png" width="112" height="28">
                    </a>

                    <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    </a>
                </div>
            </nav>
        </section>
        <ul>
            <li v-for="president in presidents" :key="president.id">
                <div class="box">
                    <p>{{ president.presidentName }}</p>
                    <img :src="imageUrl(president)" alt="" height="64" width="64" />
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: 'HomeComponent',
        data() {
            return {
                presidents: []
            }
        },
        created() {
            axios.get('/api/presidents').then((response) =>{
                this.presidents = response.data;
            });
        },
        methods: {
            imageUrl(president) {
                let path = `/images/${president.presidentNumber}.jpeg`;
                console.log(path); 
                return path;
            }
        }
    }
</script>

<style scoped>

</style>