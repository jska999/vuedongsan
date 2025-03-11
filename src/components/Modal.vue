<template>
    <div class="black-bg" v-if="is_modal_open">
        <div class="white-bg">
            <h4>상세페이지</h4>
            <img :src=clicked_room.image class="room-img">
            <p>{{ clicked_room.title }}</p>
            <p>{{ clicked_room.content }}</p>
            <p>{{ real_price }}</p>
            <p><input v-model.number="month"></p>
            <button @click="init_real_price(); month = 0; $emit('closeModal')" >닫기</button>
        </div>
    </div>
</template>

<script>
export default {
    name : 'Modal',
    data() {
        return {
            month : 0,
            real_price : parseInt(this.clicked_room.price),
        }

    },
    methods : {
        init_real_price(){
            this.month = 0;
            this.real_price = this.clicked_room.price;
        }
    },
    updated(){
        if(this.month == 2){
            alert('input 2');
        }
    },
    watch : {
        month(a){
            if(a > 12){
                alert('12 이상은 입력금지.');
                this.month = 0;
            }
            else{
                this.real_price+=a;
            }
        }
    },
    props :{
        clicked_room : Object,
        is_modal_open : Boolean,
    }
}
</script>

<style>


</style>