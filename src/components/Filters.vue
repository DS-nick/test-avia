<template>
    <div class="filters">
        <div class="filter-rates">
            <div class="filter-title">Опции тарифа</div>
            <div class="filter-list">
                <div class="filter-item">
                    <Checkbox id="1"/>
                    <span class="filter-item_text">Только прямые</span>
                </div>
                <div class="filter-item">
                    <Checkbox id="2" />
                    <span class="filter-item_text">Только прямые</span>
                </div>
                <div class="filter-item">
                    <Checkbox id="3"/>
                    <span class="filter-item_text">Только прямые</span>
                </div>
            </div>
        </div>
        <div class="filter-carriers">
            <div class="filter-title">Авиакомпании</div>
            <div class="filter-carriers_all">
                <div class="filter-item">
                    <Checkbox id="airline-all"/>
                    <span class="filter-item_text">Все</span>
                </div>
            </div>
            <div class="filter-list_carriers" >
                <div class="filter-item" v-for="(airline, index) in airlines" :key="index">
                    <Checkbox :id="index"/>
                    <span class="filter-item_text">{{ airline }}</span>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Checkbox from './Checkbox'
export default {
    name: 'Filters',
    props: {
        airlines: {
            type: Object
        }
    },
    components: {
        Checkbox
    }
    
}
</script>
<style scoped>
.filters {
    flex: 0 1 240px;
}
.filter-title {
    margin-bottom: 0.75em;
    color: #202123;
    font-weight: 700;
    line-height: 1.25em;
}
.filter-rates {
    background-color: #F5F5F5;
    border-radius: 4px;
    padding: 0.75em;
    margin-bottom: 0.75em;
}
.filter-carriers {
    background-color: #F5F5F5;
    border-radius: 4px;
    padding: 0.75em;
    padding-right: 0;
    height: 20em;
    position: relative;
    overflow-y: hidden;
   
}
.filter-list_carriers {
    overflow-y: auto;
    height: 80%;
}
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px grey; 
  border-radius: 10px;
}
::-webkit-scrollbar-thumb {
  background: red; 
  border-radius: 10px;
}
.filter-item {
    display: flex;
    line-height: 1em;
    padding: 0.5em 0;
}
.filter-item_text {
    margin-left: 0.75em;
}

</style>