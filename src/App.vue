<!-- #################################################################################### -->
<!-- ###### CURSO VUE                                                              ###### -->
<!-- ###### @author: ochoscar                                                      ###### -->
<!-- ###### @date:                                                                 ###### -->
<!-- #################################################################################### -->

<!-- #################################################################################### -->
<!-- ###### Sección de HTML                                                        ###### -->
<!-- #################################################################################### -->
<template>
  <div id="nav" class="principal">
    <span>App </span>
    <span>{{ login }}</span>
    <br/>
    <span>Age {{ age }}</span>
    <component :is="actual"></component>
    <tarjeta-datos>
      <template v-slot:slot1>
        <span>Componente en Slot</span>
      </template>
    </tarjeta-datos>
  </div>
</template>

<!-- #################################################################################### -->
<!-- ###### Sección de Script                                                      ###### -->
<!-- #################################################################################### -->
<script>
import TarjetaDatos from './components/TarjetaDatos.vue';

export default {
  components: { TarjetaDatos },
  name: 'App',
  data() {
    return {
      login: 'ochoscar',
      firstname: 'ochoscar',
      lastname: 'ochoscar',
      birthday: new Date(1984, 2, 3),
      actual: 'tarjeta-datos'
    }
  },
  computed: {
    fullname() {
        return `${this.firstname} ${this.lastname}`;
    },
    age() {
      let currentDate = new Date();
      let diff = Math.floor((currentDate - this.birthday) / 1000 / 60 / 60 / 24 / 365.25);
      return diff;
    }
  },
  methods: {
    computedAge(date) {
      let currentDate = new Date();
      let diff = currentDate - date;
      return diff;
    }
  }
}
</script>

<!-- #################################################################################### -->
<!-- ###### Sección de Estilos                                                     ###### -->
<!-- #################################################################################### -->
<style>
  .principal {
    background-color: #b93434;
    padding: 10px;
    color: white;
    border-radius: 5px;
    width: 500px;
    font-size: 3rem;
    text-align: center;
  }
</style>



