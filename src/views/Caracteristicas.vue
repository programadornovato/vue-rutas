<template>
  <div class="caracteristicas">
    <h1>caracteristicas desde vista</h1>
    <router-link 
    v-for="(car,index) of listaCar"
    :to="{name: 'caracteristicas',params:{id:car}}"
    :key="index"
    > {{car}} </router-link>
    <ComCaracteristicas/>
    <button @click="home" >Home</button>
    <button @click="atras" >Atras</button>
    <button @click="adelante" >Adelante</button>
  </div>
</template>

<script>
import ComCaracteristicas from "../components/ComCaracteristicas.vue"
export default {
  components:{
    ComCaracteristicas
  },
  data(){
    return{
      listaCar:[1,2,3]
    }
  },
  methods:{
    home(){
      this.$router.push("/")
    },
    atras(){
      this.$router.go(-1)
    },
    adelante(){
      this.$router.go(1)
    },
  }
}
</script>