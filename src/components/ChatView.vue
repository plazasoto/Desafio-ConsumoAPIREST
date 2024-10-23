<template>
  <div v-for="(mensaje, index) in mensajes" :key="index">
    <p class="message" 
    :class="{ 
      'message--left': mensaje.lado == 'left',
      'message--right': mensaje.lado == 'right'
    }"
    :style="{ 'background-color': mensaje.color }">
      <span class="fw-light"> {{ mensaje.usuario }} </span><br>
      {{ mensaje.texto }}
    </p>

  </div>
</template>

<script>
  export default {
    props:{
      mensajes: [],
    },
  }
</script>

<style scoped>
  .message{
    display: block;
    width: 50%;
    border-radius: 5px;
    text-align: center;
  }

  .message--left{
    float:left;
    margin-right: 50%;
  }
  
  .message--right{
    float: right;
    margin-left: 50%;
  }
</style>