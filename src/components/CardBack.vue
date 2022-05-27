<template>
<div id="card-back" class="container" v-show="!visible" @click="onFlip(img)">
    <header>
    <h2>Header</h2>
    </header>
    <body>
    <h3>Body</h3>
    </body>
    <footer>
    <h4>Footer</h4>
    </footer>
</div>
</template>

<script>
export default {
    name: 'CardBack',
    props: {
        visible: Boolean
    },
    methods: {
        onFlip() {
            this.$emit('toggle-visible')
        }
    },
}
</script>

<style>
.container {
    width: auto;
    height: auto;
}
</style>
