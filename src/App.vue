<template>
  <div id="app" class="container">
    <div class="row">
      <UserView @mensaje-enviado="registrarMensajeIzquierda"/>
      <ChatView :mensajes="mensajesRegistrados"/>
      <UserView @mensaje-enviado="registrarMensajeDerecha" />
    </div>
  </div>
</template>

<script>
import UserView from './components/UserView.vue'
import ChatView from './components/ChatView.vue'

export default {
  name: 'App',
  components: {
    UserView,
    ChatView
  },

  data(){
    return{
      mensajesRegistrados: [],
    }
  },

  methods:{
    registrarMensaje(mensajeRecibido, lado){
      //enviar a ChatView
      console.log(mensajeRecibido, lado);
      this.mensajesRegistrados.push(mensajeRecibido);
    },

    registrarMensajeIzquierda(mensajeRecibido){
      this.registrarMensaje(mensajeRecibido, 'left');
    },

    registrarMensajeDerecha(mensajeRecibido){
      this.registrarMensaje(mensajeRecibido, 'right');
    },
  }
}
</script>

<style>

</style>
