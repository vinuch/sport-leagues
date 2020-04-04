<template>
  <div class="home">
    <v-content>
      <v-container fluid>
        <v-row>
          <v-col cols="3">
            <v-card
              class="score-board"
              max-width="300"
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
                  <v-col cols="4" class="py-0">
                    <v-card flat tile height="100">
                      <v-img src="@/assets/man-utd-badge-png.png" aspect-ratio="1" width="50"></v-img>
                      <span class="caption text-center">Manchester</span>
                    </v-card>
                  </v-col>
                  
                  <v-col cols="4" class="py-0">
                    <span class="display-2 d-block text-center"> 2:0</span>
                    <span class="subtitle-2 text-center d-block">36'</span>
                  </v-col>

                  <!-- <v-spacer></v-spacer> -->
                  <v-col cols="4" class="py-0">
                    <v-card flat tile height="100">
                    <v-img src="@/assets/chelsea-fc-logo.png" aspect-ratio="1" width="50"></v-img>
                    <span class="caption text-center">Chelsea</span>
                  </v-card>
                  </v-col>
                </v-row>

                <v-row class="pt-1">
                  <v-col cols="3" class="py-0">
                    <v-btn text class="grey lighten-3 grey--text">
                      <v-icon>star</v-icon>
                    </v-btn>
                  </v-col>
                  <v-col cols="3" class="py-0">
                    <v-btn text class="deep-purple ligten-1 white--text">
                      Bet
                    </v-btn>
                  </v-col>
                  <v-col cols="6" class="py-0">
                    <v-btn text width="110px" class="grey lighten-3 grey--text">
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

          <v-col cols="6"  >
            <v-card flat class="banner pa-2">
              <v-row>
                <v-col cols="8">
                   <v-list-item three-line>
                    <v-list-item-content class="white--text">
                      <v-list-item-title class="title">Win $100 000 with a Free Prediction</v-list-item-title>
                      <v-list-item-subtitle class="overline grey--text lighten-5">
                        Predict the first goal of two different teams in two selected matches and win up to $100 000
                      </v-list-item-subtitle>
                      <v-btn class="white primary--text my-3" max-width="180">MORE DETAILS</v-btn>
                    </v-list-item-content>
                    

                  </v-list-item>
                </v-col>
                <v-col cols="3">
                  <v-img class="banner-image" src="@/assets/mbappe.png" aspect-ratio="1.5" width="338px" height="" contain></v-img>
                </v-col>
              </v-row>
            </v-card>

            <h2 class="my-6">Matches</h2>

            <v-card outlined class="table">
              <v-card-title>
                <v-btn text class="primary--text caption">All Matches</v-btn>
                <v-btn text class="caption">Live Play</v-btn>
                <v-btn text class="caption">Completed</v-btn>
                <v-btn text class="caption">Scheduled</v-btn>
                <v-spacer></v-spacer>
                <v-btn text>
                  <v-icon>event_note</v-icon>
                </v-btn>
              </v-card-title>
                <v-divider></v-divider>
              <v-simple-table height="300px">
              <template v-slot:default>
                <thead>
                  <tr class="grey lighten-4">
                    <th class="text-left">Date</th>
                    <th class="text-left">Match</th>
                    <th class="text-left">1x</th>
                    <th class="text-left">X</th>
                    <th class="text-left">2x</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="item in matches" :key="item.name">
                    <td class="subtitle-2 ">{{ item.time }} <v-icon size="8"  class="px-1" :class="{'primary--text' : item.date === 'Today', 'orange--text' : item.date === 'Completed', 'grey--text' : item.date === 'Cancelled'}">fiber_manual_record</v-icon> <span class="grey--text">{{ item.date }}</span></td>
                    <td class="subtitle-2">{{ item.home }} -:- {{ item.away }}</td>
                    <td class="pa-0"><v-btn small depressed>{{ item.odds.home }}</v-btn></td>
                    <td class="pa-0"><v-btn small depressed>{{ item.odds.X }}</v-btn></td>
                    <td class="pa-0"><v-btn small depressed>{{ item.odds.away }}</v-btn> <v-btn small depressed><v-icon>bar_chart</v-icon></v-btn></td>
                    
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
            </v-card>
          </v-col>

          <v-col cols="3" >
            <v-card tile class="ticket grey lighten-3" outlined>
              <v-card-title>Invoice for payment</v-card-title>
              <v-container>
                <v-card flat class="white">
                  <div class="ticket-header">
                    <span class="font-weight-bold mr-3 title">Simple</span><span class="switch"><span class="ball primary"></span></span> <span class="font-weight-bold grey--text ml-3 title">Combo</span>
                  </div>
                  <!-- <v-list-item-group>
                    <v-list-item>
                      <span>Arsenal vs Chelsea</span>
                      <v-spacer></v-spacer>
                      <v-icon>cancel</v-icon>
                    </v-list-item>
                  </v-list-item-group> -->
                </v-card>
              </v-container>
            </v-card>
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
      ],
      matches: [
        {date: 'Today', time: '8:00', home: 'Arsenal', homelogo: 'man-utd-badge-png.png', away: 'Chelsea', odds: {home :1.63, X: 1.50, away: 2.00}},
        {date: 'Today', time: '8:00', home: 'Arsenal', away: 'Chelsea', odds: {home :1.63, X: 1.50, away: 2.00}},
        {date: 'Cancelled', time: '8:00', home: 'Arsenal', away: 'Chelsea', odds: {home :1.63, X: 1.50, away: 2.00}},
        {date: 'Completed', time: '8:00', home: 'Arsenal', away: 'Chelsea', odds: {home :1.63, X: 1.50, away: 2.00}},
        {date: 'Today', time: '8:00', home: 'Arsenal', away: 'Chelsea', odds: {home :1.63, X: 1.50, away: 2.00}}
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

  .banner.pa-2.v-card.v-card--flat.v-sheet.theme--light,
  .score-board.v-card.v-card--outlined.v-sheet.theme--light,
  .leagues.v-card.v-card--outlined.v-sheet.theme--light,
  .table.v-card.v-card--outlined.v-sheet.theme--light {
    border-radius: .8rem;
    
  }
  .banner.pa-2.v-card.v-card--flat.v-sheet.theme--light{
    background: linear-gradient(0.45turn,#633eeb, #633eeb, #8462fb);
  }
  .banner-image {
    position: absolute;
    left: 22rem;
    top: -30px;
  }

  .league-item {
    border-bottom: 1px solid #eeeeee;
  }
  .league-item .v-list-item__content {
    padding: 7px;
  }
  .switch {
    padding: 4px 30px;
    border-radius: 4rem;
    border: 1px solid #dadada;
    position: relative;
  }
  .ball {
    padding: 1px 10px;
    border-radius: 50%;
    position: absolute;
    left: 4px;
    top: 4px;
    height: 20px;
  }
  .ticket-header {
    text-align: center;
    padding: 1rem;
    border-bottom: 1px dashed #dadada;
  }
</style>
