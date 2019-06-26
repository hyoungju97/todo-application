<template>
    <div>
       <transition-group tag="ul" name="todo">
       <!-- <ul> -->
           <li v-for="(todoItem,index) in todolist" v-bind:key="index">
               <span>{{ todoItem }}</span>
               <button v-on:click="removeTodoItem(todoItem, index)">remove</button>
           </li>
       <!-- </ul> -->
       </transition-group>
    </div>
</template>

<script>
export default {
    props: ['todolist'],
    
    //  data() {
    //     return {
    //         todoItems: []           
    //     }
    //  },
    methods: {
        // fetchTodoItems: function(){          
        //     for (var i=0; i<localStorage.length; i++){
        //         console.log(localStorage.length);
        //         var item = localStorage.key(i);
        //         this.todoItems.push(item);
        //     }
        // },
         removeTodoItem: function(todo, index){
            console.log('deleted',todo, index);
            this.$emit('remove',todo, index)
          //  this.todolist.splice(index,1);
            //브라우저 저장소 삭제
           // localStorage.removeItem(todo);
             // 서버의 데이터 삭제
             //axios.delete();

         },
    },
    // //컴포넌트가 생성되자마다 실행되는 로직
    // created: function(){
    //     this.fetchTodoItems();
    // },
}
</script>

<style>
.list-item {
  display: inline-block;
  margin-right: 10px;
}
.todo-enter-active, .todo-leave-active {
  transition: all 1s;
}
.todo-enter, .todo-leave-to /* .list-leave-active below version 2.1.8 */ {
  opacity: 0;
  transform: translateY(30px);
}
</style>
