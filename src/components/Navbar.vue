<template>
  <div>
    <v-app-bar outlined flat app color="white" class="nav">



      
        <ul class="nav-links d-flex">
          <li v-for="link in links" :key="link.text" class="nav-link">
            <router-link  text  class="text-capitalize "  router :to="link.route">{{ link.text }}</router-link>
          </li>
          
        </ul>
        <v-spacer></v-spacer>
        <ul class="nav-links d-flex">
            <li class="nav-link">
            <v-icon>notifications</v-icon>
          </li>
          <li class="nav-link">
            Mary
          </li>
        </ul>
        <!-- <v-divider></v-divider> -->
        


     
      
     
    </v-app-bar>
    <v-divider></v-divider>

    <v-navigation-drawer
      v-model="drawer"
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
        <v-list-item class="primary--text" router to="dashboard">
          <v-list-item-icon >
            <v-icon>dashboard</v-icon>
          </v-list-item-icon>
          <v-list-item-title>
            dashboard
          </v-list-item-title>
        </v-list-item>
        <v-list-item>
          <v-icon>subscriptions</v-icon>
        </v-list-item>
        <v-list-item>
          <v-icon>star</v-icon>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item class="primary--text" v-for="sport in sports" :key="sport.name" router :to="sport.name">
          <v-list-item-icon class="py-5">
            <v-icon  size="27">{{ sport.icon }}</v-icon>
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
  color: grey;
  font-weight: bold;
}
.nav-link a:hover, .nav-link a.router-link-exact-active {
  color: black; 
}
.nav-link a.router-link-exact-active::before{
  margin-top: 2px solid black;
}

.sidebar a.primary--text.v-list-item--active.v-list-item.v-list-item--link.theme--light {
  border-left: 4px solid #603ce9;
}
  .v-toolbar__content{
  border-bottom: 3px solid black ;
}
</style>