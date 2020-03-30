<template>
  <div class="home">
    <v-content>
      <v-container fluid>
        <v-row>
          <v-col cols="3">
            <v-card
              class=""
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
                <v-container>

                
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
          </v-col>

          <v-col cols="5" >
            <v-card outlined="">hi</v-card>
          </v-col>

          <v-col cols="3" >
            <v-card outlined>hello</v-card>
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
  components: {
  
  }
}
</script>
