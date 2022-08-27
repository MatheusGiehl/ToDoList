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
  vertical-align: baseline;
  font-family: inherit;
  font-weight:inherit;
  color: inherit;
  -webkit-appearance: none;
  appearance: none;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; 
}

body {
  font: 14px 'Helvetica Neue', Helvetica, Arial, sans-serif;
  line-height: 1.4rem;
  background: #F5F5F5;
  color: #4D4D4D;
  min-width: 230px;
  max-width: 550px;
  margin: 0 auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-weight: 300;
}

:focus {
  outline: 0;
}

.cep {
  text-decoration: none;
  font-size: 16px;
  display: block;
  padding: 5px;
  border-top:1px solid #EDEDED;
  text-align: center;
}

.hiden {
  display: none;
}

.todoapp {
  background: #FFF;
  margin: 130px 0 40px 0;
  position: relative;
  box-shadow: 0 2px 4px 0 rgba(0,0,0,0.2),
              0 25px 50px 0 rgba(0,0,0,0.2)      
}

.todoapp h1 {
  position: absolute;
  top: -155px;
  width: 100%;
  font-size: 100px;
  font-weight: 100;
  text-align: center;
  color: rgba(175,47,47,0.15);
  text-rendering: optimizeLegibility;
  -webkit-rendering: optimizeLegibility;
  -moz--rendering: optimizeLegibility;
}

</style>