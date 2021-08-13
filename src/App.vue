<template>
  <div class="container">
    <h1 class="title">Crea una tarea nueva</h1>
      <div class="input">
      <label>Tareas</label>
      <input type="text" v-model="newTarea" placeholder="Ingrese nueva tarea"/>
      <button @click="addNewTarea">Crear</button>
    </div>
    <h1 class="title">Lista</h1>
    <ul>
      <li v-for="(Tarea, index) in Tareas" :key="index">
        {{index}} : {{Tarea}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data: () => ({
    newTarea: "",
    Tareas: ["Despertar"],
  }),
  methods: {
    addNewTarea() {
      this.Tareas.push(this.newTarea);
      this.newTarea = "";
    },
  }
}
</script>

<style>
body {
  font-family: sans-serif;
}
  .container {
    display:flex;
    flex-direction: column;
    align-items: center;
  }
  .input * {
    margin: 0 0.3em;
  }
  .title {
    color: #808080
  }
</style>
