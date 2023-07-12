<template>
  <div>
    <H1>INTEGRANTES RAUL MANUEL CERVANTES</H1>
    <H2>DIPLOMADO USIP FULLSTACK</H2>
  </div>
</template>

<script>
export default {
  name: 'Popup',
  props:{
    idhijo:null
  },
  data(){

  },
  methods:{
    emitirmensaje(id){
      this.idhijo=id;
      alert("el componente hijo recibio"+this.idhijo);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
