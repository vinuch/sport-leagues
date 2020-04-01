<template>
  <div class="home">
    <v-content>
      <v-container fluid>
        <v-row>
          <v-col cols="3">
            <v-card
              class="score-board"
              max-width="320"
              outlined
            >

              <v-list-item>
                <v-list-item-content>
                  <v-list-item-title class="subtitle-2">UEFA Champions League</v-list-item-title>
                  <v-list-item-subtitle class="caption">Group stage - Matchday 2 of 6</v-list-item-subtitle>
                </v-list-item-content>
              
              <v-btn
              text
              class="red--text red lighten-5">
                <v-icon class="red--text">live_tv</v-icon>
                Live
              </v-btn>
              </v-list-item>
          
              <v-list-item class="pa-0">
                <v-container fluid>

                
                <v-row>
                  <v-col cols="4" >
                    <v-card flat tile height="100">
                      <v-img src="@/assets/man-utd-badge-png.png" aspect-ratio="1" width="50"></v-img>
                      <span class="caption text-center">Manchester</span>
                    </v-card>
                  </v-col>
                  
                  <v-col cols="4" class="px-0">
                    <span class="display-2 d-block text-center"> 2:0</span>
                    <span class="subtitle-2 text-center d-block">36'</span>
                  </v-col>

                  <!-- <v-spacer></v-spacer> -->
                  <v-col cols="4" class="">
                    <v-card flat tile height="100">
                    <v-img src="@/assets/chelsea-fc-logo.png" aspect-ratio="1" width="50"></v-img>
                    <span class="caption text-center">Chelsea</span>
                  </v-card>
                  </v-col>
                </v-row>

                <v-row class="pt-1">
                  <v-col cols="3">
                    <v-btn text class="grey lighten-3 grey--text">
                      <v-icon>star</v-icon>
                    </v-btn>
                  </v-col>
                  <v-col cols="3">
                    <v-btn text class="deep-purple ligten-1 white--text">
                      Bet
                    </v-btn>
                  </v-col>
                  <v-col cols="6">
                    <v-btn text class="grey lighten-3 grey--text">
                      Watch
                    </v-btn>
                  </v-col>
                </v-row>
            </v-container>

            
              </v-list-item>
            <v-divider></v-divider>
            <p class="subtitle-2 text-center grey--text py-2 mb-0">Match Details</p>


            </v-card>
            
            <v-subheader class="mt-3">
              <h2>Football Leagues</h2>
              <v-spacer></v-spacer>
              <v-icon>mdi-dots-horizontal</v-icon>
            </v-subheader>

            <v-card outlined class="leagues">
              <v-list class="py-0">
              <v-list-item-group>
                <v-list-item class="league-item" v-for="(league, index) in footballLeagues" :key="index">
                  <v-list-item-avatar>
                    <v-img :src="require(`@/assets/${league.logo}`)"></v-img>
                  </v-list-item-avatar>
                  <v-list-item-content>
                    <v-list-item-title class="subtitle-2"> {{ league.name }} </v-list-item-title>
                    <v-list-item-subtitle class="caption"> {{ league.country }} </v-list-item-subtitle>
                  </v-list-item-content>

                  <span class="grey--text" body-2> {{ league.TeamsAmount }}</span>
                </v-list-item>
              </v-list-item-group>
            </v-list>
            </v-card>
          </v-col>

          <v-col cols="6" >
            <v-card flat class="banner primary pa-3">
              <v-row>
                <v-col cols="8">
                   <v-list-item three-line>
                    <v-list-item-content class="white--text">
                      <v-list-item-title class="title">Win $100 000 with a Free Prediction</v-list-item-title>
                      <v-list-item-subtitle class="overline grey--text lighten-5">
                        Predict the first goal of two different teams in two selected matches and win up to $100 000
                      </v-list-item-subtitle>
                      <v-btn class="white primary--text my-3" depressed large>MORE DETAILS</v-btn>
                    </v-list-item-content>
                    

                  </v-list-item>
                </v-col>
                <v-col cols="4">
                  <v-img class="banner-image" src="@/assets/mbappe.png" aspect-ratio="1.5" width="350px" height="" contain></v-img>
                </v-col>
              </v-row>
            </v-card>
          </v-col>

          <v-col cols="3" >
            <v-card tile class="ticket grey lighten-3" outlined>hello world</v-card>
          </v-col>
        </v-row>
      </v-container>

    <v-card>
      
    </v-card>
  
  </v-content>  
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Dashboard',
  data() {
    return {
      footballLeagues: [
        {name: 'Premier League', country: 'England', TeamsAmount: 29, logo: 'Premier-League-Logo.png'},
        {name: 'Laliga', country: 'Barcelona', TeamsAmount: 13, logo: 'laliga.png'},
        {name: 'The Football League', country: 'Spain', TeamsAmount: 52, logo: 'football-league.png'},
        {name: 'Football League- Liga 3', country: 'Indonesian', TeamsAmount: 22, logo: 'liga3.png'},
        {name: 'Italian Seria A', country: 'Juventuss', TeamsAmount: 16, logo: 'seria-a.png'},
        {name: 'Bundesliga', country: 'Borussia Dortmund', TeamsAmount: 34, logo: 'bundesliga.png'},
      ]
    }
  },
  components: {
  
  }
}
</script>

<style scoped>
  .ticket {
    position: fixed;
    top: 65px;
    right: 0;
    width: 300px;
    height: 100vh;
  }

  .banner.primary.pa-2.v-card.v-card--flat.v-sheet.theme--light,
  .score-board.v-card.v-card--outlined.v-sheet.theme--light,
  .leagues.v-card.v-card--outlined.v-sheet.theme--light {
    border-radius: .8rem;
  }
  .banner-image {
    position: absolute;
    left: 350px;
    top: -30px;
  }

  .league-item {
    border-bottom: 1px solid #eeeeee;
  }
</style>
