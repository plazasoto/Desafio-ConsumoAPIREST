<template>
    <div v-for="(usuario,i) in usuarios" :key="i" class="col-3">
      <img :src="usuario.picture.large">
      <h3>{{usuario.name.first+" "+usuario.name.last}}</h3>
      <form @submit.prevent="enviarMensaje(usuario.name.first+' '+usuario.name.last)">
        <input type="color" name="" id="" v-model="mensaje.color">
        <textarea name="" id="" cols="30" rows="10" v-model="mensaje.texto"></textarea>
        <button>Enviar</button>
      </form>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  data(){
    return {
      usuarios: [],
      mensaje:{
        usuario:"",
        texto:"",
        color:"#"+ Math.floor(100 + Math.random()*155).toString(16)+ Math.floor(100 + Math.random()*155).toString(16)+ Math.floor(100 + Math.random()*155).toString(16),
      }
    }
  },

  methods:{
    async fetchUser(){
        const url = "https://randomuser.me/api";
        const { data } = await axios.get(url);
        this.usuarios = data.results
    },

    enviarMensaje(nombre){
      if(this.mensaje.texto!=""){

        this.mensaje.usuario = nombre;
        this.$emit('mensaje-enviado', structuredClone(this.mensaje));

        this.mensaje.texto = "";
      }
    }
  },

  async mounted() {
    await this.fetchUser();
  },
}
</script>

<style scoped>
  div *{
    display: block;
  }
</style>