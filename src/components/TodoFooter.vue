<template>
    <div>
        <button v-on:click="clearAll">clear all</button>
    </div>
</template>

<script>


export default {
    methods: {
        clearAll: function(){
            this.$emit('clear');
        }
    }

}
</script>

<style>

</style>
