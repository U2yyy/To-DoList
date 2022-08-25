<template>
  <div id="table">
<!--实现所有任务的展示    -->
    <transition-group
    appear
    name="animate__animated animate__bounce"
    enter-active-class="animate__backInRight"
    leave-active-class="animate__backOutRight"
    >
        <ListMission 
        v-for="todo in todos" 
        :key="todo.id" 
        :todoObj="todo" 
        :selectList="selectList" 
        :deleteList="deleteList" 
        />
    </transition-group>
  </div>
</template>

<script>
import ListMission from "@/components/ListMission";
export default {
  name: "TodoList",
  components:{ListMission},
  props:['todos','selectList','deleteList']
}
</script>
<style scoped>
  #table{
    height: auto;
  }
</style>