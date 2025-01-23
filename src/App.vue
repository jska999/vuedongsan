<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <div class="menu">
        <a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
    </div>
    <div>
        <h4>{{ products[0] }}</h4>
        <p>50만원</p>
        <button @click="report_cnt++">허위매물신고</button>
        <span>신고수 : {{ report_cnt }}</span>        
    </div>
    <div>
        <h4>{{ products[1] }}</h4>
        <p>50만원</p>
        <button>허위매물신고</button>
        <span>신고수 : 0</span>        
    </div>
    <div>
        <h4>{{ products[2] }}</h4>
        <p>50만원</p>
        <button>허위매물신고</button>
        <span>신고수 : 0</span>        
    </div>
</template>

<script>

export default {
    name: 'App',
    data() {
        return {
            menus: ["Home", "Products", "About"],
            products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
            report_cnt : 0,
        }
    },
    components: {

    }

}
</script>

<style>
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
