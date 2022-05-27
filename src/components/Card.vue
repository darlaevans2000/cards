<template>
    <div class="card"> 
        <CardFront @toggle-visible="$emit('toggle-visible')" :visible="visible" :src="img" />
        <CardBack @toggle-visible="$emit('toggle-visible')" :visible="visible" />
    </div>

</template>

<script>
import CardFront from "./CardFront.vue";
import CardBack from "./CardBack.vue";
export default {
    name: 'Card',
    props: {
        img: String,
        visible: Boolean,
    },
    components: {
    CardFront,
    CardBack,
    },
    emits: ['toggle-visible'],
    
}
</script>

<style>
.card {
    border: double;


}
</style>