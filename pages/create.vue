<template>
    <v-container
    style="width:80%; margin-left: 8%;"
    >
        <v-container>
            <h1
            style="text-align:center; margin-top:10%; background-color:#073b5b; color:white; padding-top: 1%; padding-bottom:1%"
            >
                Nova Universidade
            </h1>
            <v-form
                ref="form"
                v-model="valid"
                lazy-validation
                style="color:#073b5b; border:ridge; padding: 5%"
            >
                <v-text-field
                v-model="universidade"
                :rules="universidadeRules" 
                placeholder="Universidade"
                required
                outlined
                prepend-icon="mdi-school"
                style="width:80%; text-align:center; margin-left: 10%;"
                ></v-text-field>

                <v-text-field
                v-model="data"
                :rules="dataRules"
                placeholder="Dados"
                required
                outlined
                prepend-icon="mdi-information"
                style="width:80%; text-align:center; margin-left: 10%;"
                ></v-text-field>

            </v-form>
            <v-container
            style="background-color:#073b5b; text-align:center; padding-bottom:2%; padding-top:2%"
            >
                <v-btn
                color="info"
                class="mr-4"
                to="/"
                >
                Voltar
                </v-btn>

                <v-btn
                :disabled="!valid"
                color="success"
                class="mr-4"
                @click="validate"
                >
                Confirmar
                </v-btn>
                
                <v-btn
                color="error"
                class="mr-4"
                @click="reset"
                >
                Limpar
                </v-btn>

            </v-container>
            </v-container>
        </v-container>
</template>

<script>
export default {
    name: 'IndexPage',
    layout: 'default',

    data: () => ({
      valid: true,
      universidade: '',
      universidadeRules: [
        v => !!v || 'Nome da Universidade é necessário!',
      ],
      data: '',
      dataRules: [
        v => !!v || 'Dados da Universidade é necessário!',
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
    },
  }
</script>