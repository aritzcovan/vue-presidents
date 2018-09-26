<template>
    <div class="container">

        <nav class="navbar">
            <div class="navbar-brand">
                <img src="../assets/presidentSeal.png" style="padding: 2em;" ><br>
                <a class="navbar-item" href="#">Login</a>
                <a class="navbar-item" href="#">Vice Presidents</a>
                <a class="navbar-item" href="#">Add President</a>

                <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                </a>
            </div>
        </nav>
        
        <section class="section">
            <div class="columns">
                <div class="column is-3">
                    <label for="name">Name: </label>
                    <input type="text" class="input">

                    <label for="name">number: </label>
                    <input type="number" min="1" class="input">

                    
                    <label for="name">party: </label>
                    <select class="input"> 
                        <option  v-for="party in parties" :value="party">{{ party }}</option>
                        
                    </select>
                </div>

                <div class="column">
                    <div class="box" v-for="president in presidents" :key="president.id">
                        <article class="media">
                            <div class="media-left">
                                <figure class="image is-128x128">
                                    <img class="is-rounded" :src="imageUrl(president)"/>
                                </figure>
                            </div>
                            <div class="media-content">
                                <div class="content">
                                    <p><strong>{{ president.presidentName }}</strong></p>
                                    <span><small>years served: {{ president.yearsServed }}</small></span><br>
                                    <span><small>party: {{ president.partyAffiliation }}</small></span><br>
                                    <span><small># vps: {{ president.vicePresidents.length }}</small></span>
                                </div>
                            </div>
                            <div class="media-right">
                                <span class="icon" title="edit">
                                    <i class="fas fa-edit"></i>
                                </span>
                                <span class="icon" title="delete">
                                    <i class="fas fa-trash"></i>
                                </span>
                            </div>
                        </article>
                    </div>   
                </div>
                <div class="column is-3"></div>
            </div>
        </section>

        <footer class="footer">
        <div class="content has-text-centered">
            <p>
            <strong>The Presidents</strong> -- A web app created with VueJS and Bulma authored by <a href="https://ritzcovan.com">Alex Ritzcovan</a><div class="br"></div> The source code is licensed
            <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. 
            </p>
        </div>
        </footer>

    </div>
</template>

<script>
    import axios from "axios";
    export default {
        name: 'HomeComponent',
        data() {
            return {
                presidents: [],
                parties: ['republican', 'democrat', 'federalist', 'whig', 'democrat-republican', 'none']
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

<style>
    .icon {
        cursor: pointer;
    }
</style>