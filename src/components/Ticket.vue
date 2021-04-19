<template>
    <div class="ticket">
        <div class="ticket-info">
        <div class="ticket-carrier_logo">
            <img :src="logoUrl + flight.itineraries[0][0].carrier + '.png'" alt="" srcset="">
        </div>
        <div class="ticket-carrier_name">{{ flight.itineraries[0][0].carrier_name }}</div>
        <div class="ticket-depart_date">{{flight.itineraries[0][0].dep_date}}</div>
        <div class="ticket-timeline"></div>
        <div class="ticket-arrive_date">{{flight.itineraries[0][0].arr_date}}</div>
        </div>
        <div class="ticket-price"></div>
    </div>
</template>
<script>
export default {
    props: {
        flight: {
            type: Object
        }
    },
    data() {
        return {
            logoUrl: "https://aviata.kz/static/airline-logos/80x80/"
        }
    },
    created() {
        console.log('flight', this.flight[0])
    }
    
}
</script>
<style scoped>
.ticket {
   background-color: white;
   border-bottom: 1px solid black;
   display: flex;
}
.ticket-info {
    flex: 1;
}
.ticket-carrier_logo {
    width: 1.5em;
    height: 2em;
}
.ticket-carrier_logo img{
    width: 100%;
}
.ticket-price {
    background-color: gray;
    flex-basis: 24em;
}
</style>