<template>
  <div id="app" class="container">
    <div class="row">
      <div class="col-3">
        <UserView @mensaje-enviado="registrarMensajeIzquierda" />
      </div>
      <div class="col-6">
        <ChatView :mensajes="mensajesRegistrados" />
      </div>
      <div class="col-3">
        <UserView @mensaje-enviado="registrarMensajeDerecha" />
      </div>
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
      //enviar a ChatView mediante prop
      mensajeRecibido.lado = lado;
      this.mensajesRegistrados.push(mensajeRecibido);
    },

    //anexar lado del usuario
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
