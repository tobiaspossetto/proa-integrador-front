<template>
  <div class="tasks">

   

    <Task v-for="tarea in tareas" :key="tarea.id" :titulo='tarea.titulo' :descripcion='tarea.descripcion'/>




  </div>

  
</template>

<script>

// v-for props promesas fetch 

//TODO: Agregar el autor y fecha como prop al componente Task
//TODO: Crear un formulario para crear nueva tarea (method POST action: https://api-proa-integrador.herokuapp.com/) inputs name: 'titulo' 'descripcion' 'autor'



import Task from './Task'

export default {
  name: 'Tasks',
  

  components:{ Task},

  data(){
    return {
      tareas: []
    }
  },

  methods:{

  },



  //Al montarse el componente se ejecuta lo que este dentro:

  //async  --> async se usa donde se define la funcion 
  // await  se usa en las ordenes donde tenemos que esperar que se realice una operacion asincrona
  mounted: async function(){

    //Interactuar con una API 

    let respuesta = await fetch('https://api-proa-integrador.herokuapp.com/')
   
    respuesta = await respuesta.json()
   // console.log(respuesta)
    this.tareas = respuesta
  }

}
</script>


<style scoped>
.tasks{
  width: 50%;
  margin: auto;
}
</style>



//  <form action="https://api-proa-integrador.herokuapp.com/" method="POST">
//       <input type="text" placeholder="Titulo" name="titulo"/>
//       <input type="text"  placeholder="Descripcion" name="descripcion"/>
//       <input type="text"  placeholder="Autor" name="autor"/>
//       <button type="submit">Enviar</button>
//     </form>