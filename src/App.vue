<script>
import tasks from './todos'

export default {
  data() {
    return {
      tasks,
    }
  },
}
</script>

<template>
  <body data-new-gr-c-s-check-loaded="14.1274.0" data-gr-ext-installed="">
    <div id="root">
      <div class="todoapp">
        <h1 class="todoapp__title">todos</h1>
        <div class="todoapp__content">
          <header class="todoapp__header">
            <button type="button" class="todoapp__toggle-all" data-cy="ToggleAllButton"></button>
            <form>
              <input
                data-cy="NewTodoField"
                type="text"
                class="todoapp__new-todo"
                placeholder="What needs to be done?"
                value=""
              />
            </form>
          </header>
          <section class="todoapp__main" data-cy="TodoList">
            <div
              v-for="task in tasks"
              data-cy="Todo"
              class="todo"
              :class="{
                completed: task.completed,
              }"
            >
              <label class="todo__status-label"
                ><input data-cy="TodoStatus" type="checkbox" class="todo__status" checked=""
              /></label>
              <span data-cy="TodoTitle" class="todo__title">{{ task.title }}</span
              ><button type="button" class="todo__remove" data-cy="TodoDelete">×</button>
              <div data-cy="TodoLoader" class="modal overlay">
                <div class="modal-background has-background-white-ter"></div>
                <div class="loader"></div>
              </div>
            </div>
          </section>
          <footer class="todoapp__footer" data-cy="Footer">
            <span class="todo-count" data-cy="TodosCounter">1 items left</span>
            <nav class="filter" data-cy="Filter">
              <a href="#/" class="filter__link selected" data-cy="FilterLinkAll">All</a
              ><a href="#/active" class="filter__link" data-cy="FilterLinkActive">Active</a
              ><a href="#/completed" class="filter__link" data-cy="FilterLinkCompleted"
                >Completed</a
              >
            </nav>
            <button type="button" class="todoapp__clear-completed" data-cy="ClearCompletedButton">
              Clear completed
            </button>
          </footer>
        </div>
        <div
          data-cy="ErrorNotification"
          class="hidden notification is-danger is-light has-text-weight-normal"
        >
          <button data-cy="HideErrorButton" type="button" class="delete"></button
          ><br /><br /><br /><br />
        </div>
      </div>
    </div>
    <!-- <script type="module" src="/src/index.tsx"></script> -->
  </body>
</template>
