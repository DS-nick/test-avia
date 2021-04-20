<template>
    <div class="main_screen">
        <Filters :airlines="searchResult.airlines" />
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
    background-color: #D7D7D7;;
    margin: 0 auto;
    padding: 5em 0;
    display: flex;
    
}
</style>