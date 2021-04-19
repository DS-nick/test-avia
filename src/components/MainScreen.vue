<template>
    <div class="main_screen">
        <Filters />
        <TicketList :flights="searchResult.flights" />
    </div>
</template>
<script>
import TicketList from './TicketList'
import Filters from './Filters'
import json from '../assets/results.json'
export default {
    components: {
        TicketList,
        Filters
    },
    data() {
        return {
            searchResult: json
        }
    },
    created() {
        console.log(this.searchResult)
    }
}
</script>
<style scoped>
.main_screen {
    width: 80%;
    height: 100vh;
    background: yellow;
    margin: 0 auto;
    display: flex;
    
}
</style>