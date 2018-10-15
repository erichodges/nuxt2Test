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
          <v-btn class="nav-btn about-btn" to="/merit-cert" flat color="white"><h3>CM</h3></v-btn>
          <v-btn class="nav-btn" to="/scholarship" flat color="white"><h3>Scholarship</h3></v-btn>
          <v-btn class="nav-btn about-btn" to="/media" flat color="white"><h3>Media</h3></v-btn>
        </ul>
      </v-list>            
    </v-navigation-drawer>

<!-- Navigation Toolbar -->
    <v-toolbar  app :clipped-left="true" dense flat color="transparent">
        <v-toolbar-side-icon class="burger" @click="drawer = !drawer"></v-toolbar-side-icon>
        <v-toolbar-title>
          <v-btn to="/" color="transparent" flat>
          </v-btn>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-toolbar-items class="toolbar-items">
          <v-btn class="nav-btn" to="/about" flat color="white"><h3>About</h3></v-btn>
          <v-btn class="nav-btn" to="/teachers" flat color="white"><h3>Teachers</h3></v-btn>
          <v-btn class="nav-btn" to="/calendar" flat color="white"><h3>Calendar</h3></v-btn>
          <v-btn class="nav-btn" to="/forms-docs" flat color="white"><h3>Forms/Docs</h3></v-btn>
          <v-btn class="nav-btn" to="/merit-cert" flat color="white"><h3>CM</h3></v-btn>
          <v-btn class="nav-btn" to="/scholarship" flat color="white"><h3>Scholarship</h3></v-btn>
          <v-btn class="nav-btn" to="/media" flat color="white"><h3>Media</h3></v-btn>
          <div class="toolbar-spacer"></div>
        </v-toolbar-items>
    </v-toolbar>  
<!-- End Navigation Toolbar -->
    <div class="div-with-background">

      <nuxt />
      
      <Footer />
    </div>
  </v-app>
</template>

<script>
  import Footer from '~/components/Footer'
  export default {
    components: {
      Footer
    },
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
/* disable-resize-watcher  - this keeps the app from adding the navigation-drawer on wider screens  */

  * {
  box-sizing: border-box; }

html {
  font-family: 'Neue Haas Grotesk W01 Disp', Helvetica, sans-serif;
  line-height: 1;
  font-size: 100%;
  font-weight: 600;
  text-rendering: optimizeLegibility;
  -webkit-font-kerning: normal;
  font-kerning: normal;
  -webkit-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
}

.nav-btn {
  margin-top: 3px !important;
}

.v-toolbar__title:not(:first-child) {
      margin-left: 0 !important;
    }

@media only screen and (max-width: 60rem) {
  .toolbar-items {    
    visibility: hidden !important;
    display: none;
    width: 0 !important;
  }
}

@media only screen and (min-width: 60rem) {
  .burger {
    left: -1rem;
    visibility: hidden !important;
    display: none;
    width: 0 !important;   
  }
  .v-toolbar__content, .v-toolbar__extension {
  padding: 0 !important;
  }

}

.toolbar-spacer {
  margin-right: 2rem;
}

.burger-drawer {
  margin-top: 5px;
  margin-left: 1.2rem;
}

/* Side Nav  */
.sidenav-ul {
  padding-left: 1rem; 
}

.sidenav-link-style {
  cursor: pointer;
  font-size: 1rem;
  list-style: none;
  margin: 10px;
  text-decoration: none;
  
}

.about-btn .v-btn__content {
  justify-content: left;
}
/* End Side Nav */

.pageup-btn {
  bottom: +2rem;
}

.div-with-background {
  height: 100vh; 
  /* background-image: url('~/static/images/575839.jpg');       */
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;

  @media (min-width: 1920px) and (max-width: 2500px){
    background-image: url('/images/575839-75pc.jpg');
  }

  @media (min-width: 1400px) and (max-width: 1920px) {
    background-image: url('/images/575839-1920px.jpg');
  }

  @media (min-width: 1099px) and (max-width: 1400px) {
    background-image: url('/images/575839-1400px.jpg');
  }

  @media (min-width: 900px) and (max-width: 1099px) {
    background-image: url('/images/575839-1099px.jpg');
  }

  @media (min-width: 752px) and (max-width: 899px) {
    background-image: url('/images/575839-900px.jpg');
  }

  @media (min-width: 400px) and (max-width: 752px) {
    background-image: url('/images/575839-752px.jpg');
  }

  @media (min-width: 300px) and (max-width: 651px) {
    background-image: url('/images/575839-651px.jpg');
  }

  @media (min-width: 2500px) and (max-width: 3799px) {
    background-image: url('/images/575839-75pc.jpg');
  }

  @media (min-width: 3800px) {
    background-image: url('/images/575839-100pc.jpg');
  }
}

/* this removes all caps from the buttons */
  #app .v-btn {
    text-transform: none;
  }


</style>
