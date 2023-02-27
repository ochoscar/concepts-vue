<!-- #################################################################################### -->
<!-- ###### CURSO VUE                                                              ###### -->
<!-- ###### @author: ochoscar                                                      ###### -->
<!-- ###### @date:                                                                 ###### -->
<!-- #################################################################################### -->

<!-- #################################################################################### -->
<!-- ###### Sección de HTML                                                        ###### -->
<!-- #################################################################################### -->
<template>
    <div>
      <transition name="efecto" mode="out-in">
        <div id="nav" class="tarjeta" :key="indice">
          <span :key="indice" > {{ datos[indice] }} </span>
        </div>
      </transition>
      <div>
        <slot name="slot1"></slot>
      </div>
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
      background: rgb(152, 152, 197);
      color: white;
      border-radius: 5px;
      font-size: 3rem;
      text-align: center;
      margin: 5px;
    }

    .efecto-enter {
      opacity: 0;
    }

    .efecto-enter-active {
      transition: opacity 1s ease-out;
      animation: efecto-in 0.4s ease-out forwards;
    }

    .efecto-leave-active {
      transition: opacity 0.5s ease-out;
      animation: efecto-out 0.2s ease-out forwards;
      opacity: 1;
    }

    .efecto-leave {
    }

    @keyframes efecto-in {
      0% {
        transform: scaleY(0);
      }
      70% {
        transform: scaleY(1.4);
      }
      100% {
        transform: scaleY(1);
      }
    }

    @keyframes efecto-out {
      from {
        transform: scaleY(1);
      }
      to {
        transform: scaleY(0);
      }
    }
  </style>
  