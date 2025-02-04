<template>
    <div class="black-bg" v-if="is_modal_open">
        <div class="white-bg">
            <h4>상세페이지</h4>
            <p>내용</p><button @click="is_modal_open=false">닫기</button>
        </div>
    </div>
    <div class="menu">
        <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
    </div>
    <div>
        <img src="./assets/images/room0.jpg" class="room-img">
        <h4 @click="is_modal_open = true">{{ products[0] }}</h4>
        <p>50만원</p>
        <button @click="increse(0)">허위매물신고</button>
        <span>신고수 : {{ report_cnt[0] }}</span>        
    </div>
    <div>
        <img src="./assets/images/room1.jpg" class="room-img">
        <h4>{{ products[1] }}</h4>
        <p>50만원</p>
        <button @click="increse(1)">허위매물신고</button>
        <span>신고수 : {{ report_cnt[1] }}</span>        
    </div>
    <div>
        <img src="./assets/images/room2.jpg" class="room-img">
        <h4>{{ products[2] }}</h4>
        <p>50만원</p>
        <button @click="increse(2)">허위매물신고</button>
        <span>신고수 : {{ report_cnt[2] }}</span>        
    </div>
</template>

<script>

export default {
    name: 'App',
    data() {
        return {
            is_modal_open : false,
            menus: ["Home", "Products", "About"],
            products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
            report_cnt : [0,0,0],
        }
    },
    components: {

    },
    methods: {
        increse(no) {
            this.report_cnt[no]++;
        }
    },

}
</script>

<style>
body{
    margin: 0;
}

div {
    box-sizing: border-box;
}

.black-bg {
    width: 100%; height: 100%;
    background-color: rgba(0,0,0,0,5);
    position: fixed;
    padding: 20px;
}

.white-bg {
    width: 100%;
    background: white;
    border-radius: 8px;
    padding: 20px;
}

.room-img{
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
