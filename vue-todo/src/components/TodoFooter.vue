<template>
    <div class="clearAllContainer">
        <span class="clearAllBtn" v-on:click="clearTodo">Clear all</span>
    </div>
</template>

<script>
export default {
    methods: {
        clearTodo(){
            this.$emit('clearAll');
        }
    },
}
</script>

<style scoped>
.clearAllContainer{
    width: 10.5rem;
    height: 50px;
    line-height: 50px;
    background-color: white;
    border-radius: 5px;
    margin: 0 auto;
}
.clearAllBtn{
    color: #e20303;
    display: block;
}
</style>