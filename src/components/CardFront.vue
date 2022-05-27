
<template>
    <img v-show="visible" id="card-front" @click="onFlip()"/>
</template>

<script>
export default {
    name: 'CardFront',
    props: {
        visible: Boolean,
    },
    methods: {
        onFlip() {
            this.$emit('toggle-visible')
        }
    },
}
</script>


<style>
img {
    width: 15vw;
    height: 100%;
    object-fit: cover;
}
</style>