<template>
  <v-card max-width="800" class="mx-auto">
    <v-system-bar color="pink darken-2" dark>
      <v-spacer></v-spacer>

      <v-icon>mdi-window-minimize</v-icon>

      <v-icon>mdi-window-maximize</v-icon>

      <v-icon>mdi-close</v-icon>
    </v-system-bar>

    <v-app-bar dark color="pink">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Next Rocket Launches Schedule</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-container>
      <v-row dense>
        <v-col cols="12">
          <v-card color="#385F73" dark>
            <v-card-title class="text-h5"> Next Lauch </v-card-title>

            <v-card-subtitle class="text-h6">Mission Name - Feb 14</v-card-subtitle>
            <v-card-text v-text="nextLaunch.vehicle_name + nextLaunch.space_agency"/>
            <v-card-text v-text="nextLaunch.launch_pad_name + nextLaunch.counrty"/>

            <v-card-subtitle>
              Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo.
              Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo.
              Launch description will be here, solo del mas prixmo.
              Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo.
              Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo.
              Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo.
            </v-card-subtitle>

            

            <v-card-actions>
              <v-btn text> Go to live streaming o embebido ? </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>

        <v-col v-for="(item, i) in items" :key="i" cols="12">
          <v-card :color="item.color" dark>
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title
                  class="text-h5"
                  v-text="item.mission_name + item.date"
                ></v-card-title>

                <v-card-text v-text="item.vehicle_name"></v-card-text>
                <v-card-text v-text="item.space_agency"></v-card-text>
                <v-card-text v-text="item.launch_pad_name"></v-card-text>
                <v-card-text v-text="item.counrty"></v-card-text>

                <!--<v-card-actions>
                  <v-btn
                    v-if="item.artist === 'Ellie Goulding'"
                    class="ml-2 mt-3"
                    fab
                    icon
                    height="40px"
                    right
                    width="40px"
                  >
                    <v-icon>mdi-play</v-icon>
                  </v-btn>

                  <v-btn v-else class="ml-2 mt-5" outlined rounded small>
                    START RADIO
                  </v-btn>
                </v-card-actions>-->
              </div>

              <v-avatar class="ma-8" size="200" tile>
                <v-img :src="item.src"></v-img>
              </v-avatar>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>


<script>
export default {
  data: () => ({
    items: [
      {
        color: "#1F7087",
        src: require('../assets/telescope.svg'),
        mission_name: "Mission name",
        date: " - Feb 14",
        vehicle_name: "Vehicle name",
        space_agency: "Agency name",
        launch_pad_name: "Pad name",
        counrty: "country",
      },
      {
        color: "#952175",
        src: "https://cdn.vuetifyjs.com/images/cards/halcyon.png",
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
      {
        color: "#952175",
        src: "https://cdn.vuetifyjs.com/images/cards/halcyon.png",
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
      {
        color: "#952175",
        src: "https://cdn.vuetifyjs.com/images/cards/halcyon.png",
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
    ],
    nextLaunch: {
        mission_name: "Mission name",
        date: " - Feb 14",
        vehicle_name: "Vehicle name",
        space_agency: " - Agency name",
        launch_pad_name: "Pad name",
        counrty: " - country",
    }
  }),
};
</script>
