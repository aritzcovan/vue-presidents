<template>

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

</template>

<script>
    export default {
        name: 'PresidentListItem',
        props: ['president'],
        methods: {
             imageUrl(president) {
                return `/images/${president.presidentNumber}.jpeg`;
            }
        }
    }
</script>

<style scoped>

</style>