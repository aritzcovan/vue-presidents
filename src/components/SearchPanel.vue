<template>
    <div>
        <label for="name">name: </label>
        <input type="text" class="input">

        <label for="name">number: </label>
        <input type="number" min="1" class="input">

        
        <label for="name">party: </label>
        <select class="input"> 
            <option  v-for="(party, key) in parties" :value="party" :key="key">{{ party }}</option>
        </select>
    </div>
</template>

<script>
    export default {
        name: 'SearchPanel',
        data() {
            return {
                parties: ['republican', 'democrat', 'federalist', 'whig', 'democrat-republican', 'none']
            }
        }
    }
</script>

<style scoped>

</style>