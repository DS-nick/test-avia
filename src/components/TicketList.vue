<template>
    <ul class="tickets">
        <li class="ticket-item" v-for="flight in flights" :key="flight.id" >
            <Ticket :flight="flight" />
        </li>
    </ul>
</template>
<script>
import Ticket from './Ticket'
export default {
    props: {
        flights: {
            type: Array
        }

    },
    components: {
        Ticket
    },
    created() {
        console.log('**', this.flights)
    }
}
</script>
<style scoped>
.tickets {
    list-style: none;
    flex: 1 1;
    margin-left: 1.75em;
}
.ticket-item {
    margin-bottom: 0.75em;
}
</style>