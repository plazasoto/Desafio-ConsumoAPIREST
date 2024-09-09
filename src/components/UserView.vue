<template>
    <div v-for="(usuario,i) in usuarios" :key="i">
        <img :src="usuario.picture.large">
        <h3>{{usuario.name.first+" "+usuario.name.last}}</h3>
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