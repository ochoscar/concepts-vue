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
    <span>App</span>
    <span>{{ login }}</span>
    <span>Age {{ age }}</span>
    <Entrada></Entrada>
  </div>
</template>

<!-- #################################################################################### -->
<!-- ###### Sección de Script                                                      ###### -->
<!-- #################################################################################### -->
<script>
import Entrada from '@/components/Entrada.vue'

export default {
  name: 'App',
  componetnts: { Entrada },
  data() {
    return {
      login: 'ochoscar',
      firstname: 'ochoscar',
      lastname: 'ochoscar',
      birthday: new Date(1984, 2, 3)
    }
  },
  computed: {
    fullname() {
        return `${this.firstname} ${this.lastname}`;
    },
    age() {
      let currentDate = new Date();
      let diff = currentDate - this.birthday;
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
    width: 100px;
    font-size: 3rem;
    text-align: center;
  }
</style>



