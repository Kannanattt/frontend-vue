<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
       text
       @click="goTologin()"
      >
        <span class="mr-2">Login</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>

      <v-btn
        text
        @click="goTomanage()"
      >
      หน้าจัดการข้อมูล


      </v-btn>
      <v-btn
        text
        @click="goToConnect()"
      >
      Connect Backend


      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
  methods: {
    goTologin () {
      this.$router.push({ path:'/login'}).catch(()=>{})
    },
    goTomanage () {
      this.$router.push({ path:'/manageTable'}).catch(()=>{})
    },
    goTotableStudent() {
      this.$router.push({ path:'/tableStudent'}).catch(()=>{})
    }
  }
}
</script>