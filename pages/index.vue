<template>
<v-container
  style="margin-top:5%"
>
<v-card
  style="border:ridge"
  outlined
>
    <v-card-title
      style="color:#073b5b; margin-left:1%"
    >
      Universidades
      <v-spacer></v-spacer>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Buscar"
        single-line
        hide-details
      ></v-text-field>
      <v-spacer></v-spacer>
      <v-btn
          color="#073b5b"
          dark
          class="mb-2"
          v-bind="attrs"
          v-on="on"
          style="margin-right:1%;"
        >
          Nova Universidade
        </v-btn>
    </v-card-title>
    <hr>
    <v-data-table
      :headers="headers"
      :items="universities"
      :search="search"
    >
    <template v-slot:item.actions="{ item }">
      <v-icon
        small
        class="mr-2"
        @click="editItem(item)"
        style="color: #25abb3"
      >
        mdi-pencil
      </v-icon>
      <v-icon
        small
        @click="deleteItem(item)"
        style="color: #cf5751"
      >
        mdi-delete
      </v-icon>
    </template>
    </v-data-table>
  </v-card>
</v-container>
</template>


<script>
export default {
  name: 'IndexPage',
  layout: 'default',
    data () {
      return {
        search: '',
        headers: [
          {
            text: 'Nome',
            align: 'center',
            sortable: true,
            value: 'name',
          },
          { text: 'Dados', sortable: false, value: 'data' },
          { text: 'Actions', value: 'actions'}
        ],
        universities: [
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
          {
            name: 'Universidade',
            data: 'dados',
          },
        ],
      }
    },
    methods: {
      editItem (item) {
        this.editedIndex = this.desserts.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialog = true
      },

      deleteItem (item) {
        this.editedIndex = this.desserts.indexOf(item)
        this.editedItem = Object.assign({}, item)
        this.dialogDelete = true
      },
    }
  }
</script>
