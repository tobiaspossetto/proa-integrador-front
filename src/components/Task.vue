<template>
  <div class="container-task">
    <h3>{{titulo}}</h3>
    <p>{{descripcion}}</p>
  </div>
</template>

<script>



export default {
  name: 'Tasks',

  props: ['titulo', 'descripcion']
}
</script>
<style>
.container-task{
    width: 50%;
    
    border: 1px solid rgb(19, 19, 29);
    background: #1f1f1f;
    color: #e6e6e6;
    margin: 10px auto;

    text-align: center;
}
</style>