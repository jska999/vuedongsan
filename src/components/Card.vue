<template>
    <div>
        <img :src=oneroom.image class="room-img">
        <h4 @click="$emit('openModal', oneroom)">{{ oneroom.title }}</h4>
        <p>{{ oneroom.price }}</p>
    </div>
</template>

<script>
export default {
    name: 'Card',
    data() {
        return {

        }
    },
    props: {
        oneroom: Object,
    }



}
</script>
<style>
</style>
