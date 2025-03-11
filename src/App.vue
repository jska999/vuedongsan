<template>

    <Modal :clicked_room="clicked_room" :is_modal_open="is_modal_open" @closeModal="is_modal_open=false"/>

    <discount v-if="is_showDiscount" />

    <div class="menu">
        <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
    </div>
    <button @click="priceSort()">가격순정열</button>

    <div v-for="(oneroom, i) in onerooms" :key="i">
        <Card :oneroom="oneroom" @openModal="showModal($event)"/>
    </div>
<!--
    <div v-for="(oneroom, i) in onerooms" :key="i">
        <img :src=oneroom.image class="room-img">
        <h4 @click="showModal(oneroom)">{{ oneroom.title }}</h4>
        <p>{{ oneroom.price }}</p>
    </div>
-->    
</template>

<script>
import data from './oneroom.js';
import discount from './discount.vue';
import Modal from './components/Modal.vue';
import Card from './components/Card.vue';

export default {
    name: 'App',
    data() {
        return {
            is_showDiscount:true,
            is_modal_open: false,
            menus: ["Home", "Products", "About"],
            onerooms: data,
            onerooms_org: data,
            clicked_room: Object,
        }
    },
    components: {
        discount : discount,
        Modal : Modal,
        Card,
    },
    mounted() {
        setTimeout(()=>{
            this.is_showDiscount = false;
        }, 2000);
    },
    methods: {
        increse(no) {
            this.report_cnt[no]++;
        },
        showModal(clicked) {
            this.clicked_room = clicked;
            this.is_modal_open = true;
        },
        priceSort(){
            this.onerooms.sort(function(a,b) {
                return a - b;
            })
        }
    },

}
</script>

<style>
body {
    margin: 0;
}

div {
    box-sizing: border-box;
}

.discount {
    background: #eee;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
}

.black-bg {
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0, 5);
    position: fixed;
    padding: 20px;
}

.white-bg {
    width: 100%;
    background: white;
    border-radius: 8px;
    padding: 20px;
}

.room-img {
    width: 100%;
    margin-top: 40px;
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 20px;
}

.menu {
    background: darkslateblue;
    padding: 15px;
    border-radius: 5px;
}

.menu a {
    color: white;
    padding: 10px;
}
</style>
