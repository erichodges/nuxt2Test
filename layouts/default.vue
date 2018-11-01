<template>
  <v-app dark>
    <v-navigation-drawer dark class="drawer"
      :mini-variant.sync="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      temporary
      disable-resize-watcher
      fixed
      app
      width=180
    >
      <v-list>
        <v-icon class="burger-drawer" @click="drawer = !drawer">close</v-icon>
        <ul class="sidenav-ul">
          <v-btn class="nav-btn about-btn" to="/about" flat color="white"><h3>About</h3></v-btn>
          <v-btn class="nav-btn" to="/teachers" flat color="white"><h3>Teachers</h3></v-btn>
          <v-btn class="nav-btn" to="/calendar" flat color="white"><h3>Calendar</h3></v-btn>
          <v-btn class="nav-btn" to="/forms-docs" flat color="white"><h3>Forms/Docs</h3></v-btn>
          <v-btn class="nav-btn" to="/scholarship" flat color="white"><h3>Scholarship</h3></v-btn>
          <v-btn class="nav-btn about-btn" to="/media" flat color="white"><h3>Media</h3></v-btn>
        </ul>
      </v-list>            
    </v-navigation-drawer>
<!-- Navigation Toolbar -->
    <v-toolbar app :clipped-left="true" dense flat color="primary" :scrollOffScreen="true">
        <v-toolbar-side-icon class="burger" @click="drawer = !drawer"></v-toolbar-side-icon>
        <v-toolbar-title>
          <v-btn to="/" color="transparent" flat>
          <img src="/images/mtac-logo.png" alt="MTAC Marin"></v-btn>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="toolbar-items">
          <v-btn class="nav-btn" to="/about" flat color="white"><h3>About</h3></v-btn>
          <v-btn class="nav-btn" to="/teachers" flat color="white"><h3>Teachers</h3></v-btn>
          <v-btn class="nav-btn" to="/calendar" flat color="white"><h3>Calendar</h3></v-btn>
          <v-btn class="nav-btn" to="/forms-docs" flat color="white"><h3>Forms/Docs</h3></v-btn>
          <v-btn class="nav-btn" to="/scholarship" flat color="white"><h3>Scholarship</h3></v-btn>
          <v-btn class="nav-btn" to="/media" flat color="white"><h3>Media</h3></v-btn>
          <div class="toolbar-spacer"></div>
        </v-toolbar-items>
    </v-toolbar>  
<!-- End Navigation Toolbar -->  
    <div>
      <nuxt /> 
    </div>
    <v-footer class="footerTwo" dark height="auto">
      <div class="caption copy">
        &copy;2018 MTAC Marin
      </div>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: true,
        drawer: false,
        fixed: false,
        miniVariant: false,
        right: false,
        rightDrawer: false,
        title: 'Nuxt/Vuetify'
      }
    }
  }
</script>


<style lang="scss">

/* this removes all caps from the buttons */
  #app .btn {
    text-transform: none !important;
    color: #4e4e4e;
  }

.about-btn .v-btn__content {
  justify-content: left;
}


.copy {
  margin-left: 1.3rem;
  padding: 5px 5px;
}

.footerTwo {
  margin-top: auto;
}
</style>
