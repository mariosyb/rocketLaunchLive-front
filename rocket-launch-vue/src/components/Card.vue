<template>
<div id="app" v-bind:style="{ backgroundColor: color}">
  <v-card max-width="800" class="mx-auto" v-bind:style="{ backgroundColor: color2}">
    <v-system-bar color="black" dark>
      <v-spacer></v-spacer>
    </v-system-bar>

    <v-app-bar dark color="grey darken-4">

      <v-toolbar-title>Next Rocket Launches Schedule</v-toolbar-title>

      <v-spacer></v-spacer>
    </v-app-bar>

    <v-container>
      <v-row dense>
        <v-col cols="12">
          <v-card color="blue-grey darken-4" dark>
            <v-card-title class="text-h5"> Next Lauch </v-card-title>

            <v-card-subtitle class="text-h6">Mission Name - Feb 14</v-card-subtitle>
            <v-card-text v-text="nextLaunch.vehicle_name + nextLaunch.space_agency"/>
            <v-card-text v-text="nextLaunch.launch_pad_name + nextLaunch.counrty"/>

            <v-card-subtitle v-text="nextLaunch.description"/>

            <v-card-actions>
              <v-btn elevation="5" text>Go to live stream</v-btn>
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
</div>
</template>


<script>
export default {
  data: () => ({
    items: [
      {
        color: "blue darken-3",
        src: require('../assets/rocket3.svg'),
        mission_name: "Mission name",
        date: " - Feb 14",
        vehicle_name: "Vehicle name",
        space_agency: "Agency name",
        launch_pad_name: "Pad name",
        counrty: "country",
      },
      {
        color: "deep-purple darken-3",
        src: require('../assets/rocket4.svg'),
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
      {
        color: "blue darken-3",
        src: require('../assets/rocket2.svg'),
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
      {
        color: "deep-purple darken-3",
        src: require('../assets/rocket1.svg'),
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
        description: "Launch description will be here, solo del mas prixmo. Launch description will be here, solo del mas prixmo Launch description will be here, solo del mas prixmo."
    },
    color: '#EEEEEE',
    color2: "#C5CAE9"
  }),
};
</script>
