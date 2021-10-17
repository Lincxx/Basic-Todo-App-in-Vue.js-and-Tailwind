<template>
 <div class="bg-gray-300 h-screen w-width flex flex-col justify-center items-center">
        <div class="header">
            <h1 class="text-4xl">My Todo App with Tailwind and Vue</h1>
   
            <div class="form flex">
                <input
                    @keyup="checkAdd" 
                    v-model="newTodo"
                    class="shadow appearance-none border  w-full py-2 px-3 text-gray-700 leading-tight " id="newText" type="text" placeholder="Add new todo">
                <button 
                    @click="add"
                    id="newBtn" 
                    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 ">
                    Add
                </button>
            </div>
        </div>
        <div class="todos w-10/12 mt-8">
            <div class="pendings" v-if="totalPendings>0">
                <h3 class="text-2xl">Pendings: {{ totalPendings }}</h3>
                <ul id="pendingList">
                    <li 
                        v-for="(pending, index) in pendingList" 
                        :key="index"
                        @click="moveToCompleted(pending, index)"
                        class="text-center p-3 bg-white shadow-lg mt-4 cursor-pointer hover:bg-green-400">
                        {{ pending }}
                    </li>
                </ul>
            </div>
            <div class="completed mt-8" v-if="totalCompleted>0">
                <h3 class="text-2xl">Completed: {{ totalCompleted }}</h3>
                <ul id="completedList">
                    <li 
                        v-for="(completed, index) in completedList" 
                        :key="index"
                         @click="moveToPending(completed, index)"
                        class="text-center line-through  text-red-500 p-3 bg-white shadow-lg mt-4  cursor-pointer hover:bg-red-400 hover:text-white ">
                        {{ completed }}
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>


export default {
  name: 'App',
  data() {
      return {
          newTodo: '',
          pendingList:[],
          completedList:[]
      }
  },
  computed:{
      totalPendings(){
          return this.pendingList.length
      },
      totalCompleted(){
          return this.completedList.length
      },
  },
  methods:{
      add(){
          if(this.newTodo !== ""){
              this.pendingList.push(this.newTodo)
              this.newTodo = ''
          }
          else {
              alert('Please specify the task to Add')
          }
          
      },
      checkAdd(event){
          if(event.key.toLowerCase() === 'enter'){
            this.add();  
          }
      },
      moveToCompleted(todo, index){
          this.completedList.push(todo);
          this.pendingList.splice(index,1);
      },
      moveToPending(todo, index){
         this.pendingList.push(todo);
         this.completedList.splice(index, 1);
      }
  }
}
</script>


