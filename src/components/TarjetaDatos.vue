<!-- #################################################################################### -->
<!-- ###### CURSO VUE                                                              ###### -->
<!-- ###### @author: ochoscar                                                      ###### -->
<!-- ###### @date:                                                                 ###### -->
<!-- #################################################################################### -->

<!-- #################################################################################### -->
<!-- ###### Sección de HTML                                                        ###### -->
<!-- #################################################################################### -->
<template>
    <div id="nav" class="tarjeta">
      <transition name="efecto" mode="out-in">
        <span :key="indice" > {{ datos[indice] }} </span>
      </transition>
    </div>
  </template>
  
  <!-- #################################################################################### -->
  <!-- ###### Sección de Script                                                      ###### -->
  <!-- #################################################################################### -->
  <script>
  export default {
    name: 'TarjetaDatos',
    data() {
      return {
        datos: ['VUE', 'React', 'Java', 'Node'],
        indice: 0
      }
    },
    methods: {
      rotarMensaje() {
        this.indice++;
        if(this.indice == this.datos.length) {
          this.indice = 0;
        }
      }
    },
    mounted() {
      setInterval(this.rotarMensaje, 2500);
    }
  
  }
  </script>
  
  <!-- #################################################################################### -->
  <!-- ###### Sección de Estilos                                                     ###### -->
  <!-- #################################################################################### -->
  <style>
    .tarjeta {
      color: white;
      border-radius: 5px;
      font-size: 3rem;
      text-align: center;
    }

    .efecto-enter {
      opacity: 0;
    }

    .efecto-enter-active {
      transition: opacity 1s ease-out;
    }

    .efecto-leave-active {
      transition: opacity 0.5s ease-out;
      opacity: 0;
    }

    .efecto-leave {
    }
  </style>
  