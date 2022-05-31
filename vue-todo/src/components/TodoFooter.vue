<template>
    <div class="clearAllContainer">
        <span class="clearAllBtn" v-on:click="clearTodo">Clear all</span>
    </div>
</template>

<script>
import { mapMutations } from 'vuex';

export default {
    methods: {
        ...mapMutations({
            clearTodo: 'clearAll'
        })
        // clearTodo(){
        //     this.$store.commit('clearAll');
        //     // this.$emit('clearAll');
        // }
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