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
        <div class="ticket-price">
            <div class="ticket-price_text">{{flight.price}} ₸</div>
            <Button />
            <div class="ticket-price_description">
                Цена за всех пассажиров
            </div>
            <div class="ticket-price_baggage">
                <span class="ticket-price_baggage-info">Нет багажа</span>
                <span class="ticket-price_baggage-add">+Добавить багаж</span>
            </div>
        </div>
    </div>
</template>
<script>
import Button from './Button'
export default {
    props: {
        flight: {
            type: Object
        }
    },
    components: {
        Button
    },
    data() {
        return {
            logoUrl: "https://aviata.kz/static/airline-logos/80x80/",
            weekDays: {
                1: "пн",
                2: "вт",
                3: "ср",
                4: "чт",
                5: "пн",
                6: "суб",
                7: "вс"
            }
        }
    },
    created() {
        console.log('flight', this.flight[0])
    }
    
}
</script>
<style scoped>
.ticket {
   background-color: #fff;
   padding-left: 2.75em;
   display: flex;
   border-radius: 4px;
}
.ticket-info {
    flex: 1;
    display: flex;
    align-items: center;
}
.ticket-carrier_logo {
    width: 1.5em;
    height: 2em;
}
.ticket-carrier_logo img{
    width: 100%;
}
.ticket-carrier_name {
    color:#202123;
    font-size: 0.875em;
    margin: 0 0.75em;
}
.ticket-timeline {
    width: 20em;
    height: 0.1px;
    background-color: black;

}
.ticket-price {
    background-color: #F5F5F5;
    flex-basis: 30%;
    padding: 1.25em;
    border-top-right-radius: 4px;
    border-bottom-right-radius: 4px;
    
}
.ticket-price_text {
    color: #202123;
    font-size: 1.5em;
    line-height: 1.75em;
    font-family: Arial;
    text-align: center;
    margin-bottom: 0.75em;
}
.ticket-price_description {
    text-align: center;
    color: #707276;
    font-size: 0.75em;
    margin-top: 0.5em;
}
.ticket-price_baggage {
    margin-top: 0.75em;
    text-align: center;
    font-size: 0.75em;
}
.ticket-price_baggage-add {
    color: #5763B3;
    margin-left: 0.875em;
}
</style>