<template>
  <div class="home-page base-page">
    <CreateTodo @todo-created="onTodoCreated" />
    <div class="separator"><hr /></div>
    <ul class="todo-list">
      <TodoItem
        v-for="todoItem in todoList"
        :key="todoItem.id"
        :todo="todoItem"
        @todo-updated="onTodoUpdated"
        @todo-deleted="onTodoDeleted"
      />
    </ul>
    <!--  <ul class="todo-list">
       <li v-for="todoItem in todoList" :key="todoItem.id" class="todo-item">
        <div class="title">
          {{ todoItem.title }}
        </div>
        <div class="actions">
          <input
            type="checkbox"
            class="checkbox"
            :checked="todoItem.isCompleted"
          />
          <button>x</button>
        </div>
      </li>
    </ul> -->
  </div>
</template>

<script>
import { fetchTodoList} from "@/netClient/todoService";
import TodoItem from "@/components/TodoItem";
import CreateTodo from "@/components/CreateTodo";

export default {
  name: "HomePage",
  components: {
    CreateTodo,
    TodoItem,
  },
  data: () => ({
    todoList: [],
  }),
  created() {
    this.fetchTodoList();
  },
  methods: {
    async fetchTodoList() {
      try {
        this.todoList = await fetchTodoList();
      } catch (error) {
        console.error({ error });
      }
    },
    onTodoCreated() {
      this.fetchTodoList();
    },
    onTodoUpdated(newTodo) {
      const todo = this.todoList.find((el) => el.id === newTodo.id);
      todo.isCompleted = newTodo.isCompleted;
    },
    onTodoDeleted(id) {
      this.todoList = this.todoList.filter((el) => el.id !== id);
    },
  },
};
</script>

<style scoped>
p {
  color: #ffffff;
}
</style>
