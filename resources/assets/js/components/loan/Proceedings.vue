<template>
  <v-card flat>

    <v-card-title class="pb-0">
      <v-toolbar>
        Aquí ira el título
      </v-toolbar>
    </v-card-title>

    <v-card-title> 
      Préstamos mayores a 80.000
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Búsqueda"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>

    <v-spacer></v-spacer>

    <template>
      <v-card-text> 
        <v-data-table
          :headers="cabeceras"
          :search="search"
          :footer-props="{ itemsPerPageOptions: [8, 15, 30] }"
        >
        </v-data-table>
      </v-card-text>
    </template>

  </v-card>
</template>

<script>

export default {
  name: "proceedings-index",
  components: {
  },
  data() {
    return {
      search: '',
      cabeceras: [
        {
          text: 'Código Prestamo',
          align: 'start',
          sortable: false,
          value: 'name',
          class: ['normal', 'white--text'],
        },
        {
          text: 'Monto aprobado [Bs]',
          value: 'Monto',
          class: ['normal', 'white--text'],
        },
        {
          text: 'Nombre',
          value: 'Nombre',
          class: ['normal', 'white--text'],
        },
      ]
    }
  },
}
</script>
