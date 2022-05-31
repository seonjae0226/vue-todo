<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="fa-solid fa-plus addBtn"></i>
        </span>
        <AlertModal v-if="showModal" @close="showModal = false">
            <h3 slot="header">알림!<i class="closeModalBtn fa-solid fa-xmark" @click="showModal = false"></i></h3>
            <!-- <i class="closeModalBtn fa-solid fa-square-xmark" @click="showModal = false"></i> -->
            <h5 slot="body">할일을 입력하세요</h5>
            <h6 slot="footer">copy right</h6>
        </AlertModal>
    </div>
</template>

<script>
import AlertModal from './common/AlertModal.vue'

export default {
    data() {
        return{
            newTodoItem: "",
            showModal: false
        }
    },
    methods: {
        addTodo(){
            if(this.newTodoItem !== ''){
                this.$store.commit('addOneItem', this.newTodoItem);
                this.clearInput();
            }else{
                this.showModal = !this.showModal;
            }
        },
        clearInput(){
            this.newTodoItem = '';
        }
    },
    components: {
        AlertModal
    }
}
</script>

<style scoped>
    input:focus{
        outline: none;
    }
    .inputBox{
        background: white;
        height: 50px;
        line-height: 50px;
        border-radius: 5px;
        margin: 0 15px 0 15px;
    }
    .inputBox input{
        height: 40px;
        width: 70%;
        border-style: none;
        font-size: 0.9rem;
    }
    .addContainer{
        float: right;
        background: linear-gradient(to right, #a765fd,#735fe2);
        display: block;
        width: 3rem;
        border-radius: 0 5px 5px 0;
    }
    .addBtn{
        color: white;
        width: 50px;
        vertical-align: middle;
    }
    .closeModalBtn{
        color: #43b983;
        float: right;
    }
</style>