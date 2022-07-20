<templete>
  <section class="todoapp">
  <header class="header">
     <h1>Tarefas</h1>
     <input-task @newTask="addTask"></input-task>
     <task-list :todo-list="tasks"></taks-list>
  </<header>  
  </section>
</templete>

<script>

</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}

button {
  margin: 0;
  padding: 0;
  background: none;
  font-size: 100%;
  vertical-aling: baseline;
  font-family: inherit;
  font-weight:inherit;
  color: inherit; 
  
}
</style>