<template>
  <Main @periodSelected="(mensaje) => mensajito = mensaje.toLowerCase()"/>
    <p>{{mensajito}}</p>
  
  <div>
        <Activity />
  </div>

</template>

<script>
import Main from '@/components/Main.vue'
import Activity from '@/components/Activity'

export default {
  components: { Activity, Main },
  data() {
    return {
      mensajito: 'no mensaje' 
    }
  }

}
</script>

<style>

</style>