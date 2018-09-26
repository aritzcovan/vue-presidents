<template>
    <div>
        <div class="box" v-for="president in presidents" :key="president.id">
            <!-- president list item -->
            <president-list-item :president="president" />
        </div>   
    </div>
</template>

<script>
    import PresidentListItem from './PresidentListItem';
    export default {
        name: 'PresidentList',
        props: ['presidents'],
        components: {
            'president-list-item': PresidentListItem
        }
    }
</script>

<style scoped>

</style>