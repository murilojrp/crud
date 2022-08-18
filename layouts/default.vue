<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" style="color:#073b5b" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      :clipped-left="clipped"
      fixed
      app
      style="height:10%; padding-top: 1%;"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <h2
      style="color:#073b5b; margin-left: 1%;"
      > Universidades </h2>
      <v-spacer></v-spacer>
      <img src="../assets/6091-removebg-preview.png" width="12%" style="margin-right:22%">
      <h4
      style="color:#073b5b; margin-right: 1%;"
      > Olá "Fulano", seja bem-vindo! </h4>
      <v-avatar color="#073b5b" style="margin-right:1%">
      <v-icon 
      dark
      >
        mdi-account
      </v-icon>
      </v-avatar>
      <v-avatar color="#073b5b" style="margin-right:1%">
      <v-icon 
      dark
      >
        mdi-bell
      </v-icon>
      </v-avatar>
      <v-avatar color="#073b5b">
      <v-icon 
      dark
      >
        mdi-exit-run
      </v-icon>
      </v-avatar>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
      style="background-color:#073b5b; height: 10%;"
    >
      <span
      style="color:white; align-self:center"
      >&copy; {{ `Produzido por @MurigolArts `}}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Lista',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Criar',
          to: '/create'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Universidades'
    }
  }
}
</script>
