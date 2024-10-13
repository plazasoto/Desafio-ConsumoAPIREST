<template>
    <div v-for="(usuario,i) in usuarios" :key="i" class="col-3">
        <img :src="usuario.picture.large">
        <h3>{{usuario.name.first+" "+usuario.name.last}}</h3>

        <input type="color" name="" id="">
        <textarea name="" id="" cols="30" rows="10"></textarea>
        <button>Enviar</button>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data(){
    return {
      usuarios: []
    }
  },
  methods:{
    async fetchUser(){
        const url = "https://randomuser.me/api";
        const { data } = await axios.get(url);
        this.usuarios = data.results
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
  }/*
  div{
    display: inline-block;
  }*/
</style>