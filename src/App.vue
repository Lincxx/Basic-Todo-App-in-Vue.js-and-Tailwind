<template>
 <div class="bg-gray-300 h-screen w-width flex flex-col justify-center items-center">
        <div class="header">
            <h1 class="text-4xl">My Todo App with Tailwind </h1>
   
            <div class="form flex">
                <input class="shadow appearance-none border  w-full py-2 px-3 text-gray-700 leading-tight " id="newText" type="text" placeholder="Add new todo">
                <button id="newBtn" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 ">
                    Add
                </button>
            </div>
        </div>
        <div class="todos w-10/12 mt-8">
            <div class="pendings">
                <h3 class="text-2xl">Pendings:</h3>
                <ul id="pendingList">
                    <li class="text-center p-3 bg-white shadow-lg mt-4 cursor-pointer hover:bg-green-400">Item 1</li>
                    <li class="text-center p-3 bg-white shadow-lg mt-4 cursor-pointer hover:bg-green-400">Item 2</li>
                </ul>
            </div>
            <div class="completed mt-8">
                <h3 class="text-2xl">Completed:</h3>
                <ul id="completedList">
                    <li class="text-center line-through  text-red-500 p-3 bg-white shadow-lg mt-4  cursor-pointer hover:bg-red-400 hover:text-white ">Item 3</li>
                    <li class="text-center line-through text-red-500 p-3 bg-white shadow-lg mt-4  cursor-pointer hover:bg-red-400 hover:text-white">Item 4</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>


export default {
  name: 'App',
}
</script>


