<template>
    <div>
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
    </div>
</template>

<script>
    export default {
        name: 'HeaderComponent'
    }
</script>

<style scoped>

</style>