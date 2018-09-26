<template>
    <div class="container">
        <!-- header -->
        <header-component />       
        <section class="section">
            <div class="columns">
                <div class="column is-3">
                    <!-- search panel -->
                    <search-panel />
                </div>
                <div class="column">
                    <!-- filter panel -->
                    <filter-panel />
                    <!-- PresidentList -->
                    <president-list :presidents="presidents" />
                </div>
                <div class="column is-2"></div>
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
    import HeaderComponent from './Header';
    import SearchPanel from './SearchPanel'
    import FilterPanel from "./FilterPanel";
    import PresidentList from "./PresidentList";

    export default {
        name: 'HomeComponent',
        components: {
            'header-component'  : HeaderComponent,
            'search-panel'      : SearchPanel,
            'filter-panel'      : FilterPanel,
            'president-list'    : PresidentList
        },
        data() {
            return {
                presidents: []
            }
        },
        created() {
            axios.get('/api/presidents').then((response) =>{
                this.presidents = response.data;
            });
        }
    }
</script>

<style>
    .icon {
        cursor: pointer;
    }
</style>