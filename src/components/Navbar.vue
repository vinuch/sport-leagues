<template>
  <div>
    <v-toolbar outlined flat color="white" class="nav">



      
        <ul class="nav-links d-flex">
          <li v-for="link in links" :key="link.text" class="nav-link">
            <router-link  text  class="text-capitalize "  router :to="link.route">{{ link.text }}</router-link>
          </li>
          
        </ul>
        <v-spacer></v-spacer>
        <ul class="nav-links d-flex mr-2">
          <v-divider vertical></v-divider>
          <li class="nav-link px-3">
            <v-icon>notifications</v-icon>
          </li>
          <v-divider vertical></v-divider>
          
         </ul>   
          <div>
            
            <v-list-item two-line :class="miniVariant && 'px-0'">
            <v-list-item-avatar>
              <img src="https://randomuser.me/api/portraits/men/81.jpg">
            </v-list-item-avatar>

            <v-list-item-content style="width:10rem">
              <v-list-item-title class="subtitle-2 grey--text">Linnette Simmons</v-list-item-title>
              <v-list-item-subtitle class="subtitle-1">1823.23$ <span class="caption">6385 PLN</span></v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          
          </div>
        
        <!-- <v-divider></v-divider> -->
        


     
      
     
    </v-toolbar>
    <v-divider inset></v-divider>

    <v-navigation-drawer
      left
      app
      expand-on-hover
      permanent
      mini-variant
      primary
      width="200px"
      >

      <v-list dense nav p-y0 class="sidebar">
        <v-list-item>
          <v-icon>sort</v-icon>
        </v-list-item>
        <v-divider></v-divider>
        <v-list-item router to="dashboard">
          <v-list-item-icon >
            <v-icon class="sidebar-icon">dashboard</v-icon>
          </v-list-item-icon>
          <v-list-item-title>
            dashboard
          </v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-icon class="sidebar-icon">subscriptions</v-icon>
        </v-list-item>
        <v-list-item>
          <v-icon class="sidebar-icon">star</v-icon>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item class="sidebar-link" v-for="sport in sports" :key="sport.name" router :to="sport.name">
          <v-list-item-icon tile class="py-5">
            <v-icon class="sidebar-icon" size="30">{{ sport.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-title>{{ sport.name }}</v-list-item-title>
          
        </v-list-item>
      </v-list>
        
      
      

    </v-navigation-drawer>
  </div>

</template>

<script>
  export default {
    name: 'Navbar',
    data() {
      return {
        sports: [
          {name: 'football', icon: 'sports_soccer'},
          {name: 'volleyball', icon: 'sports_volleyball'},
          {name: 'basketball', icon: 'sports_basketball'},
          {name: 'golf', icon: 'sports_golf'},
          {name: 'console', icon: 'sports_esports'},
          {name: 'rugby', icon: 'sports_rugby'},
          {name: 'tennis', icon: 'sports_tennis'}
        ],
        links: [
          {text: 'Matches', route: '/matches'},
          {text: 'Live score', route: '/livescore'},
          {text: 'statistics', route: '/statistics'},
          {text: 'Analytics', route: '/analytics'},
          {text: 'Forecast', route: '/Forecast'},
        ],
        miniVariant: true
      }
    },
  }
</script>

<style scoped>
header.nav.v-sheet.v-sheet--tile.theme--light.v-toolbar.v-toolbar--flat.white{
  margin-left: 2rem;
}

.nav-links {
  padding: 0;
  margin: 0;
}
.nav-link {
  list-style: none;
  padding: 0 1rem;
}
.nav-link a {
  text-decoration: none;
  color: #dadada;
  font-weight: bold;
}
.nav-link a:hover, .nav-link a.router-link-exact-active {
  color: black; 
}
.nav-link a.router-link-exact-active::before{
  margin-top: 2px solid black;
}


.sidebar-link {
  margin: 3px -7.5px 0 ;
  padding: .4rem;
}
.sidebar .sidebar-icon {
  color: #dadada;
}
.theme--light.v-list {
  background-color: none !important;
}
div.v-list-item {
  padding: .4rem;

}
a.v-list-item--active.v-list-item {
  color: #603cea;
}
.v-list-item--active::before {
  background-color: transparent;
}
.v-list--nav .v-list-item{
  border-radius: 0;
}
.v-list-item--active{
  border-left: 2px solid #603cea ;
}
</style>